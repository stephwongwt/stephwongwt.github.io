---
title: Using Front Matter as a CMS in VS Code
description: Getting into gear on editing the blog in vscode and managing the content with FrontMatter within vscode!
date: 2024-10-11T15:33:11.940Z
preview: ""
tags:
  - site-update
categories:
  - jekyll
  - vscode
slug: front-matter-cms-code
layout: post
featured: true
---

I originally wanted to go through some of my old github repos today to start writing up on them. But I realized I would prefer to have a proper set up in an editor so that I can maintain a proper structure. So after a some searching, I found [FrontMatter](https://frontmatter.codes/)!

It's very straightforward, you install the extension, you initialize the dashboard, following the instructions on the welcome page, and you're good to go!

I got started with improving my previous posts' front matter metadata, adding descriptions, proper tags and categories. Then I wanted to keep the tooltip I previously created, so I created a snippet.

First the html for the tooltip:

{% raw %}

````markdown
```html
<div class="tooltip tooltip-{{ include.position }}">
  {{ include.text }}
  <div class="tooltip-text">{{ include.tooltip }}</div>
</div>
```
````

{% endraw %}

Then the snippet to be added into `frontmatter.json`:

````markdown
```json
"frontMatter.content.snippets": {
  "Tooltip": {
    "description": "Inserts a text with tooltip",
    "body": "{% raw %}{{<div>{% include tooltip.html position=\"[[position]]\" tooltip=\"[[tooltip]]\" text=\"[[text]]\" %}</div>}}{% endraw %}",
    "fields": [
      {
        "name": "position",
        "title": "position",
        "type": "choice",
        "choices": [
          "top",
          "bottom",
          "left",
          "right"
        ],
        "default": "top"
      },
      {
        "name": "tooltip",
        "title": "tooltip",
        "type": "string",
        "single": true,
        "default": ""
      },
      {
        "name": "text",
        "title": "text",
        "type": "string",
        "single": true,
        "default": ""
      }
    ]
  }
}
```
````

And to then use it, in any page, add the liquid tag.

{% raw %}

````markdown
```liquid
{% include tooltip.html position="top" tooltip="An example tooltip!" text="Mouse over here!" %}
```
````

{% endraw %}

The HTML is based off of [W3's CSS Tooltip](https://www.w3schools.com/css/css_tooltip.asp), so it's only a basic tooltip.

Some issues I faced trying to include it in this page, it can't be a part of the markdown paragraphs, as the html won't get recognized and will be rendered as part of the paragraph. And if your screen is narrower, the tooltip will also be out of the screen.

But hey FrontMatter is new to me and I am still excited to explore what else I can do with!
