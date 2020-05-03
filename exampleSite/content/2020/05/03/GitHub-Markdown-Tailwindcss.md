---
title: "GitHub Markdown Tailwindcss"
date: 2020-05-03T14:13:25+03:00
tags:
- CSS
- Hugo
links:
- 2020/05/01/tailwind-css.md
---

Due to the nature of the Tailwind CSS library there is no pre-built support for handling Markdown. Luckily, there is this GitHub repository [iandinwoodie/github-markdown-tailwindcss](https://github.com/iandinwoodie/github-markdown-tailwindcss) that has implemented support for it.

## Usage

Add class `markdown` to the element that you want to style. With Hugo you can add this kind of snippet:

```html
<div class="markdown">
	{{ .Content }}
</div>
```

