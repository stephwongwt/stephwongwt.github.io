---
title: Using Front Matter as a CMS in VS Code
description: Getting into gear on editing the blog in vscode and managing the content with FrontMatter within vscode!
date: 2024-10-11T15:33:11.940Z
preview: ""
tags:
  - update
categories:
  - jekyll
  - vscode
slug: front-matter-cms-code
layout: post
---
I originally wanted to go through some of my old github repos today to start writing up on them. But I realized I would prefer to have a proper set up in a editor so that I can maintain a proper structure. So after a bit of searching, I found [FrontMatter](https://frontmatter.codes/)!

It's very straightforward, you install the extension, you initialize the dashboard, following the instructions on the welcome page, and you're good to go!

I got started with improving my previous posts' front matter metadata, adding descriptions, proper tags and categories. Then I wanted to keep the tooltip I previously created, so I created a snippet.

{% include tooltip.html position="top" tooltip="An example tooltip!" text="Mouse over here!" %}
Above is an example tooltip, but it doesn't work very well. It can't be a part of the markdown paragraphs, as the html won't get recognized and will be rendered as part of the paragraph. And if your screen is narrower, you will notice that the tooltip will also be out of the screen.

But wow there's so much more that FrontMatter can do! I am excited to explore what else I can do with, perhaps adding some images in future. Next up though, is to fix that tooltip snippet!
