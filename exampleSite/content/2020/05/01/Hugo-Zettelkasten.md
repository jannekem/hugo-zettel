---
title: "Hugo Zettelkasten"
date: 2020-05-02T22:44:29+03:00
tags:
- Frontend
- Web development
- Hugo
- Zettelkasten
links:
- 2020/05/01/Tailwind-css.md
- 2020/05/03/GitHub-Markdown-Tailwindcss.md
- 2020/05/01/Hugo-npm.md
- 2020/05/03/Hugo.md
- 2020/05/03/Hugo-taxonomies.md
entry: true
---

Hugo theme for taking notes with the [Zettelkasten method](https://www.reddit.com/r/Zettelkasten/comments/b566a4/what_is_a_zettelkasten/).

Zettelkasten can be considered as an extension to your brain where you process and store data and make connections between ideas.

<!--more-->

## Setup

Prerequisites for Hugo Pipe's PostCSS [1][1]

```plaintext
npm install -g postcss-cli
npm install -g autoprefixer
```

## Content organization

### Tags

Add tags to the front matter of each note. This gives some categorization of topics for the note and makes it possible to find related items later if there are no direct links between notes. The tags could look like this:

```yaml
tags:
- Frontend
- Web development
- Hugo
- Zettelkasten
```

### Links

Add related links to other notes in the front matter as a list to the Markdown files. The links need to be configured as a taxonomy in the Hugo configuration. [3]

```toml
[taxonomies]
    tag = "tags"
    link = "links"
```

Example links in the fron matter:

```yaml
links:
- 2020/05/01/Tailwind-css.md
- 2020/05/03/GitHub-Markdown-Tailwindcss.md
- 2020/05/01/Hugo-npm.md
- 2020/05/03/Hugo.md
- 2020/05/03/Hugo-taxonomies.md
```

Each page contains a **File reference** at the end of the page that you can use for linking.

### Entry notes

You can add the following front matter parameter to stick the note to the front page as an entry note:

```yaml
entry: true
```



## Implementation details

The theme is based on the [Tailwind CSS starter theme][1]

Markdown rendering is based on the [github-markdown-tailwindcss][2] repository

[1]: https://github.com/dirkolbrich/hugo-theme-tailwindcss-starter/
[2]: https://github.com/iandinwoodie/github-markdown-tailwindcss
[3]: /2020/05/03/hugo-taxonomies/

