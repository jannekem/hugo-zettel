---
title: "Hugo Sort Tags by Count"
date: 2020-05-03T18:23:42+03:00
tags:
- Hugo
links:
- 2020/05/01/Hugo-Zettelkasten.md
- 2020/05/01/Hugo.md
---

I wanted to sort the tags in the "Tags" page by the count of child pages. This can be achieved by creating a `terms.html` template page. From there the data can be fetched nicely:

```go-html-template
{{ range .Data.Terms.ByCount }}
    {{ partial "widgets/tag.html" (dict "tag" .Page.Title "count" .Count)}}
{{ end }}
```

