---
title: "Hugo Taxonomies"
date: 2020-05-03T12:36:31+03:00
tags:
- Hugo
links:
- 2020/05/03/Hugo.md
---

Taxonomies are user defined groupings of content. [1][1]

Taxonomies are configured in the `config.toml` file like this

```toml
[taxonomies]
	category = "categories"
	tag = "tags"
```

The first part defines the singular form and the scond part the plural form.

Taxonomies can be accessed on special taxonomy pages or sitewide with the  `.Site.Taxonomies` variable. For example the `.Site.Taxonomies.tags` can be used to fetch a map of tags which will return a mapping of taxonomy keys with lists of pages that contain those tags.

[1]: https://gohugo.io/content-management/taxonomies/

