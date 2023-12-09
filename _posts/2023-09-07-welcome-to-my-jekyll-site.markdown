---
layout: base
title:  "Hello Jekyll"
date:   2023-09-07 17:49:18 -0700
tags: 
categories: Jekyll
color:  
---

Created for my final project for [CS50's Introduction to Computer Science](https://pll.harvard.edu/course/cs50-introduction-computer-science). 

I honestly was deep into making an app for android that I hope will make it's way to light sometime in the future but I didn't correctly estimate how long it would take and am currently stuck with some bugs I can't live with submitting for this project. 
Eventually I will make it public on my [Github](https://github.com/aliocantinea) but feel free to reach out if you think you can help and I will share more! 

A lot of this site has been cobbled together and I am sure it will change a bit over time, but my main aim was to have a desktop/mobile version (though I am not too happy with the mobile version), using the base Jekyll Minima v3 theme. Needless to say I struggled enough getting it to work that I am just submitting what I have! 

I use Obsidian for my note taking so I like the idea of having something that would work with MD files. Having a static site was also appealing because I find time and time again the tracking on a lot of modern websites annoying and not privacy focused. Who knows if I will continue to feel like this but for the time being this was the solution that fit the best for me.

Hopefully this is enough and I can continue to learn more going forward! 



This might not work going forward but the only way I was able to get things to update for me was the following cobbled together from a few different places after some intense googling. The files are included on my github but you can also refer below if it helps at all! 

###Gemfile
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

###config.yml
My config file in case you find it useful
{
    title: Type nerdy to me
    author:
    name: Bradley James
    email: "blog@bradley-james.ca"
    pronouns: "He/Him She/Her"
    description: >- # this means to ignore newlines until "baseurl:"
    My personal website where I post about things I discover about technology and figure out where I might end up in the overwhelming world of IT 
    baseurl: "" # the subpath of your site, e.g. /blog
    url: "https://bradley-james.ca" # the base hostname & protocol for your site, e.g. http://example.com

    collections:
    bookmarks:
        output: true


    # Build settings
    remote_theme: jekyll/minima

    plugins:
    - jekyll-feed
    - jekyll-seo-tag

    # Theme-specific settings

    minima:
    skin: auto
    # Minima date format.
    # Refer to https://shopify.github.io/liquid/filters/date/ if you want to customize this.
    #
    # date_format: "%b %-d, %Y"

    # Generate social links in footer.
    #
    social_links:
        - { platform: github,         user_url: "https://github.com/aliocantinea" }
        - { platform: mastodon,       user_url: "https://mastodon.social/@Aliocantinea" }
        - { platform: email,          user_url: "mailto:blog@bradley-james.ca" }
        - { platform: rss,            user_url: "https://bradley-james.ca/feed.xml" }
    #   - { platform: devto,          user_url: "https://dev.to/jekyll" }
    #   - { platform: dribbble,       user_url: "https://dribbble.com/jekyll" }
    #   - { platform: facebook,       user_url: "https://www.facebook.com/jekyll" }
    #   - { platform: flickr,         user_url: "https://www.flickr.com/photos/jekyll" }
    #   - { platform: google_scholar, user_url: "https://scholar.google.com/citations?user=qc6CJjYAAAAJ" }
    #   - { platform: instagram,      user_url: "https://www.instagram.com/jekyll" }
    #   - { platform: keybase,        user_url: "https://keybase.io/jekyll" }
    #   - { platform: linkedin,       user_url: "https://www.linkedin.com/in/jekyll" }
    #   - { platform: microdotblog,   user_url: "https://micro.blog/jekyll" }
    #   - { platform: pinterest,      user_url: "https://www.pinterest.com/jekyll" }
    #   - { platform: stackoverflow,  user_url: "https://stackoverflow.com/users/1234567/jekyll" }
    #   - { platform: telegram,       user_url: "https://t.me/jekyll" }
    #   - { platform: twitter,        user_url: "https://twitter.com/jekyllrb" }
    #   - { platform: youtube,        user_url: "https://www.youtube.com/jekyll" }

    # If you want to link only specific pages in your header, uncomment this and add the path to the pages in
    # order as they should show up.
    #
    header_pages:
        - vault.md
        - about.md

    permalink: /:title/
    show_excerpts: true

    # Syntax highlighter settings
    kramdown:
    syntax_highlighter_opts:
        default_lang: kotlin
        guess_lang: true
}