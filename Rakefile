require "html/proofer"

task default: "test"

task :test do
  sh "bundle exec jekyll build"
  HTML::Proofer.new("./_site", url_ignore: ["#"]).run
end
