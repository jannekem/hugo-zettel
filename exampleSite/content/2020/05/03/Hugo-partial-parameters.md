---
title: "Hugo Partial Parameters"
date: 2020-05-03T16:35:33+03:00
tags:
- Hugo
links:
- 2020/05/01/Hugo-Zettelkasten.md
- 2020/05/03/Hugo.md
---

When implementing the Hugo Zettel theme I wanted to extract the tag element as a reusable widget inside the theme. The input requirements are:

- tag name
- amount of posts with the tag

However, the Hugo partials only take one input parameter where we typically pass the context. However, this didn't feel like the right approach because the partial would need to know do different things based on the context it is in.

The solution turned out to be quite simple as you can pass a dictionary as the dictionary parameter which lets you define an arbitrary amount of parameters.

```go-html-template
{{ range .Params.tags }}
    {{ partial "widgets/tag" (dict "tag" .) }}
{{ end }}
```