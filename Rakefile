require "rubygems"
require "tmpdir"

require "bundler/setup"
require "jekyll"

GITHUB_REPOSITORY = "TadeasKriz/tadeaskriz.github.io"

desc "Generate blog files"
task :generate do
    Jekyll::Site.new(Jekyll.configuration({
        "source" => ".",
        "destination" => "_site"
    })).process
end

desc "Generate and publish blog to gh-pages"
task :publish => [:generate] do
    Dir.mktmpdir do |tmpdir|
        cp_r "_site/.", tmpdir

        pwd = Dir.pwd
        Dir.chdir tmpdir

        message = "Site updated at #{Time.now.utc}"

        system "git init"
        system "git add ."
        system "git commit -m #{message.inspect}"
        system "git remote add origin git@github.com:#{GITHUB_REPOSITORY}.git"
        system "git push origin master --force"

        Dir.chdir pwd
        
    end
end