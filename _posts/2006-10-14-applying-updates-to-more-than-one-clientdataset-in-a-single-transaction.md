---
title: Applying updates to more than one ClientDataSet in a single transaction with RemObjects SDK
author: Erick Sasse
layout: post
permalink: /applying-updates-to-more-than-one-clientdataset-in-a-single-transaction/
dsq_thread_id:
  - 262149463
categories:
  - Delphi
---
*Portuguese notice: Escrevi esse artigo em inglês pois o objetivo inicial é ajudar usuários do news da RemObjects com essa dúvida frequente. Mas acredito que está bem fácil de entender, mesmo para quem não domina o idioma. Em todo caso, fiquem livres para postar comentários em português pedindo esclarecimentos de algo que não entenderam.*

One of the first tricky things you face off when migrating from 2 to 3 tiers is to get rid of all transaction control on the client side. The client should not start or finish a transaction. As&nbsp;a matter of fact, the client should know nothing at all about transactions. All transaction logic should remain on the server.

This post is intended to show how to create a method in your RemObjects DataSnap server to receive a list of ClientDataSet deltas to update on the server inside a single transaction so that you can rollback all changes in case of an unexpected error during the updates.

This method is useful only when you need to apply ClientDataSets that are not nested, because DataSnap already applies nested datasets in a single transaction by default. 

You&#8217;re going to need a working RO DataSnap server, since I&#8217;m not going to cover the steps involved in building one. We are just going to add a new method to your existing service.

First you need to create some data types in your server RODL. Using RO Service Builder, create a DeltaToApply struct with ProviderName&nbsp; (string) and Delta (binary) fields:

<a href="http://static.flickr.com/103/269254526_41aeb130d8_o.png" target="_new" atomicselection="true"><img src="http://static.flickr.com/103/269254526_41aeb130d8_m.jpg" /></a> 

Then create an array of DeltaToApply:

<a href="http://static.flickr.com/115/269254527_72f30c3771_o.png" target="_new" atomicselection="true"><img src="http://static.flickr.com/115/269254527_72f30c3771_m.jpg" /></a> 

Then you have to create a method in your service that takes the array parameter. I always add&nbsp;this method to the same service that has all my providers, because we are going to need them to apply the updates:

<a href="http://static.flickr.com/98/269254528_f207cfe92a_o.png" target="_new" atomicselection="true"><img src="http://static.flickr.com/98/269254528_f207cfe92a_m.jpg" /></a> 

The implementation of this method is as follow:&nbsp;

<pre class="wp-code-highlight prettyprint">&lt;span style="color: #0000ff"&gt;procedure&lt;/span&gt; TNewService.ApplyUpdates(&lt;span style="color: #0000ff"&gt;var&lt;/span&gt; ADeltaArray: DeltaArray);
&lt;span style="color: #0000ff"&gt;var&lt;/span&gt;
  I: Integer;
  Provider: TDataSetProvider;
  ErrorCount: Integer;
&lt;span style="color: #0000ff"&gt;begin&lt;/span&gt;
  &lt;span style="color: #008000"&gt;// Put your code to start transaction&lt;/span&gt;
  &lt;span style="color: #0000ff"&gt;try&lt;/span&gt;
    &lt;span style="color: #0000ff"&gt;for&lt;/span&gt; I := 0 &lt;span style="color: #0000ff"&gt;to&lt;/span&gt; ADeltaArray.Count - 1 &lt;span style="color: #0000ff"&gt;do&lt;/span&gt;
    &lt;span style="color: #0000ff"&gt;begin&lt;/span&gt;
      Provider := FindProvider(ADeltaArray[I].ProviderName);
      &lt;span style="color: #0000ff"&gt;if&lt;/span&gt; &lt;span style="color: #0000ff"&gt;not&lt;/span&gt; Assigned(Provider) &lt;span style="color: #0000ff"&gt;then&lt;/span&gt;
        &lt;span style="color: #0000ff"&gt;raise&lt;/span&gt; Exception.Create(&#039;Provider &lt;span style="color: #0000ff"&gt;not&lt;/span&gt; found: &#039; + ADeltaArray[I].ProviderName);

      Provider.ApplyUpdates(VariantFromBinary(ADeltaArray[I].Delta), 0, ErrorCount);
      &lt;span style="color: #0000ff"&gt;if&lt;/span&gt; ErrorCount &gt; 0 &lt;span style="color: #0000ff"&gt;then&lt;/span&gt;
        &lt;span style="color: #008000"&gt;// Put your code to handle errors&lt;/span&gt;
        &lt;span style="color: #0000ff"&gt;raise&lt;/span&gt; Exception.Create(&#039;Errors during applyupdates: &#039; + Provider.Name);
    &lt;span style="color: #0000ff"&gt;end&lt;/span&gt;;
    &lt;span style="color: #008000"&gt;// Put your code to commit the transaction&lt;/span&gt;
  &lt;span style="color: #0000ff"&gt;except&lt;/span&gt;
    &lt;span style="color: #008000"&gt;// Put your code to rollback the transaction&lt;/span&gt;
    &lt;span style="color: #0000ff"&gt;raise;&lt;/span&gt;
  &lt;span style="color: #0000ff"&gt;end&lt;/span&gt;;
&lt;span style="color: #0000ff"&gt;end&lt;/span&gt;;</pre>

I have also created a helper function to find the provider by its name:

<pre class="wp-code-highlight prettyprint">&lt;span style="color: #0000ff"&gt;function&lt;/span&gt; TNewService.FindProvider(ProviderName: &lt;span style="color: #0000ff"&gt;string&lt;/span&gt;): TDataSetProvider;
&lt;span style="color: #0000ff"&gt;var&lt;/span&gt;
  Component: TObject;
&lt;span style="color: #0000ff"&gt;begin&lt;/span&gt;
  Component := FindComponent(ProviderName);
  &lt;span style="color: #0000ff"&gt;if&lt;/span&gt; Component is TDataSetProvider &lt;span style="color: #0000ff"&gt;then&lt;/span&gt;
    Result := Component as TDataSetProvider
  &lt;span style="color: #0000ff"&gt;else&lt;/span&gt;
    Result := &lt;span style="color: #0000ff"&gt;nil&lt;/span&gt;;
&lt;span style="color: #0000ff"&gt;end&lt;/span&gt;;</pre>

Ok, this is it for the server. On the client, you need to create a method that adds all ClientDataSet deltas to your array and sends it to the server:

<pre class="wp-code-highlight prettyprint">&lt;span style="color: #0000ff"&gt;procedure&lt;/span&gt; TClientForm.ApplyUpdates(ClientDataSets: &lt;span style="color: #0000ff"&gt;array&lt;/span&gt; &lt;span style="color: #0000ff"&gt;of&lt;/span&gt; TClientDataSet);
&lt;span style="color: #0000ff"&gt;var&lt;/span&gt;
  Deltas: DeltaArray;
  Delta: DeltaToApply;
  I: Integer;
&lt;span style="color: #0000ff"&gt;begin&lt;/span&gt;
  Deltas := DeltaArray.Create;
  try
    &lt;span style="color: #0000ff"&gt;for&lt;/span&gt; I := Low(ClientDataSets) &lt;span style="color: #0000ff"&gt;to&lt;/span&gt; High(ClientDataSets) &lt;span style="color: #0000ff"&gt;do&lt;/span&gt;
    &lt;span style="color: #0000ff"&gt;begin&lt;/span&gt;
      &lt;span style="color: #0000ff"&gt;if&lt;/span&gt; ClientDataSets[I].ChangeCount = 0 &lt;span style="color: #0000ff"&gt;then&lt;/span&gt;
        Continue;

      Delta := Deltas.Add;
      Delta.ProviderName := ClientDataSets[I].ProviderName;
      Delta.Delta := BinaryFromVariant(ClientDataSets[I].Delta);
    &lt;span style="color: #0000ff"&gt;end&lt;/span&gt;;
    CoNewService.Create(ROMessage, ROChannel).ApplyUpdates(Deltas);
  finally
    Deltas.Free;
  &lt;span style="color: #0000ff"&gt;end&lt;/span&gt;;
&lt;span style="color: #0000ff"&gt;end&lt;/span&gt;;</pre>

The VariantFromBinary and BinaryFromVariant are located in the uROBinaryHelpers unit.

Then you just need to call this method from the client passing all ClientDataSets you want to update on the server using a single transaction:

<pre class="wp-code-highlight prettyprint">ApplyUpdates([ClientDataSet1, ClientDataSet2, ClientDataSet3]);</pre>

That&#8217;s it! I hope it helps. If you find any problems or improvements to this code, please, let me know ASAP so that I can fix.