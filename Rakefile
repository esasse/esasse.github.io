require 'html/proofer'

task :default => 'test'

task :test do
  sh "bundle exec jekyll build"
  HTML::Proofer.new("./_site", href_ignore: ['#']).run
end
