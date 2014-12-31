---
title: ExecuteAndWait
author: Erick Sasse
layout: post
permalink: /executeandwait/
dsq_thread_id:
  - 262147644
categories:
  - Delphi
---
Hoje precisei de uma fun&ccedil;&atilde;o que executasse um aplicativo externo e aguardasse sua execu&ccedil;&atilde;o antes de continuar. Testei v&aacute;rias fun&ccedil;&otilde;es que encontrei, mas a &uacute;nica que funcionou foi essa, que aparente &eacute; de autoria de Marc Hoffman e fiz alguns ajustes:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;function ExecuteAndWait(App, Params: string): Cardinal;
var
  StartupInfo: TStartupInfo;
  ProcessInfo: TProcessInformation;
  s: array[0..MAX_PATH] of char;
begin
  GetStartupInfo(Startupinfo);

  ExpandEnvironmentStrings(pChar(App), @s, MAX_PATH);
  App := string(pChar(@s));

  if CreateProcess(pChar(App),
    pChar(App + &#039; &#039; + Params),
    nil, nil, false, 0, nil,
    pChar(GetCurrentDir),
    StartupInfo,
    ProcessInfo) then
  begin
    CloseHandle(ProcessInfo.hThread);
    WaitForSingleObject(ProcessInfo.hProcess, INFINITE);
    GetExitCodeProcess(ProcessInfo.hProcess, result);
    CloseHandle(ProcessInfo.hProcess);
  end
  else
    raise Exception.CreateFmt(&#039;N&atilde;o foi poss&iacute;vel criar o 
      processo %s %s: %d&#039;, [App, Params, GetLastError]);
end;
&lt;/code&gt;</pre>