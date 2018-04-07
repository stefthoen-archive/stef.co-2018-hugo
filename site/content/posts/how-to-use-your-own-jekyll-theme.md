---
layout: post
title:  "How To Use Your Own Jekyll Theme"
date:   2017-01-21 21:08:09 +0100
categories: howto jekyll theme
---

With Jekyll 3.0 themes can be saved as gem files, which make them trivially easy to import and use in your Jekyll website. If you want to use a theme that's available as a gem you need to edit your `Gemfile`:

{{< highlight ruby >}}
gem "minima", "~> 2.0"
{{< /highlight >}}

And you want to edit your `_config.yml`:

{{< highlight yml >}}
theme: minima
{{< /highlight >}}

Don't forget to `bundle install` to install new gems.

If you want to use your own theme and you want to keep it separate from your website, you need to make it available as a gem. Open your terminal, `cd` out of your Jekyll website and run `jekyll new-theme my-awesome-theme` and replace `my-awesome-theme` with your theme name. Jekyll will bootstrap a theme for you.

To use it in your Jekyll site, you need to edit your website's `Gemfile` and `_config.yml` as mentioned above, and publish your theme on [RubyGems.org](http://rubygems.org). [Follow the steps](https://jekyllrb.com/docs/themes/#publishing-your-theme) in the official Jekyll guide to learn how to do that. 

If you're not ready to publish your gem, and you have your theme hosted on Github or something like it, you can pull in your gem by pointing your `Gemfile` to a Git repository, like so:

{{< highlight ruby >}}
gem "epoch", :git => 'git@github.com:stefthoen/epoch.git'
{{< /highlight >}}

Or you can point it to your theme's local path, like so:

{{< highlight ruby >}}
gem "epoch",  path: "~/Sites/epoch"
{{< /highlight >}}

Don't forget to install your gems with `bundle install`. There some more ways to install gems. Go to [bundler.io](http://bundler.io/gemfile.html) to learn more about it.
