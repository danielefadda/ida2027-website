source "https://rubygems.org"

gem "jekyll", "~> 3.10.0"
gem "nokogiri", "~> 1.16.8"
gem "kramdown", "~> 2.4.0"
gem "kramdown-parser-gfm", "~> 1.1.0"

group :production do
  gem "github-pages", "~> 232"
  gem "jekyll-remote-theme", "~> 0.4.3"
end

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17.0"
  gem "jekyll-seo-tag", "~> 2.8.0"
  gem "jekyll-sitemap"
  gem "jekyll-include-cache", "~> 0.2.1"
end

gem "chulapa-jekyll"
gem "faraday-retry"

platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

platforms :mingw, :x64_mingw, :mswin do
  gem "wdm", "~> 0.1.1"
end

platforms :jruby do
  gem "http_parser.rb", "~> 0.6.0"
end
