---
layout: base
title:  "Remote Minima theme v3"
date:   2023-09-14 17:49:18 -0700
tags:   vault
categories: bookmarks
color:  
---

This might not work going forward but the only way I was able to get things to update for me was the following cobbled together from a few different places after some intense googling. The files are included on my github but you can also refer below if it helps at all! 

### Gemfile
{
    source "https://rubygems.org"

    # Since it is pulling from the theme repo though it could break
    # But it seems to take forever for it to ever get updates 
    gem "jekyll", github: "jekyll/jekyll"
    gem "jekyll", ENV["JEKYLL_VERSION"] if ENV["JEKYLL_VERSION"] 
    gem "kramdown-parser-gfm" if ENV["JEKYLL_VERSION"] == "~> 3.9"

    # This is the default theme for new Jekyll sites. You may change this to anything you like.
    gem "minima", git: "https://github.com/jekyll/minima"

    # I had to leave github-pages commented out or this broke again.
    #gem "github-pages", group: :jekyll_plugins
    # If you have any plugins, put them here!
    group :jekyll_plugins do
    gem "jekyll-feed"
    gem "jekyll-remote-theme"
    end

    # Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
    # and associated library.
    platforms :mingw, :x64_mingw, :mswin, :jruby do
    gem "tzinfo", ">= 1", "< 3"
    gem "tzinfo-data"
    end

    # Performance-booster for watching directories on Windows
    gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]

    # Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds since newer versions of the gem
    # do not have a Java counterpart.
    gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
}
