---
title: Overhauling the theme
description: Upgraded to al-folio theme with some customizations
date: 2024-11-03T15:08:24.534Z
preview: ""
tags:
  - jekyll
categories:
  - site-update
layout: post
slug: overhauling-theme
---

So after setting up FrontMatter, I thought I was good to go.

Nope. I took a look at some other themes and felt that they were closer to the look and feel I prefer, and so I began to overhaul the site.

Following [Maruan's al-folio](https://github.com/alshedivat/al-folio) theme, I took parts of what I wanted and used it on my blog. However I had a small setback as I'm working on Windows as well as my Jekyll version being different from the one al-folio was using.

Firstly the gem `libv8-node` was not available on Windows and its dependency `mini-racer` was also not support on WSL / CYGWIN / MINGW. Upon searching for the error, I found [this page](https://github.com/alshedivat/al-folio/issues/691) which outlined the same issues I faced, and saw a solution to omit `mini-racer` from my Gemfile and ensure I had NodeJs installed. That helped, and I am able to serve the page locally as I did previously.

Aside from this solution, I also tried using the devcontainer provided by al-folio and that worked as well! But to continue to be able to use FrontMatter in the container environment, I had to add its extension ID into the customization > vscode > extensions into `devcontainer.json`.

That's a really cool solution to allow different developers to have the same development experience in a containerized environment.

So spent the majority of my day cleaning up any unnecessary pages, files and other things provided, and then embellishing details where required.

I also edited my previous post to ensure it still make sense, and learnt to add the {% raw %}`{% raw %}`{% endraw %} and `{{ "{% endraw " }}%}` tags to ensure liquid doesn't process any tags in-between those raw tags. Or using quotation marks like {% raw %}`{{ "{{ this " }}}}`{% endraw %} to escape them.
