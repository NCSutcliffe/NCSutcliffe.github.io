source "https://rubygems.org"

# Same Jekyll major version GitHub Pages builds with
gem "jekyll", "~> 3.10"
gem "kramdown-parser-gfm"
gem "liquid", ">= 4.0.4"   # 4.0.3 breaks on Ruby 3.2+ (tainted? error)

group :jekyll_plugins do
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
  gem "jekyll-feed"
end

# Libraries newer Ruby versions no longer bundle, which Jekyll 3 still needs
gem "csv"
gem "base64"
gem "bigdecimal"
gem "logger"
gem "webrick"
