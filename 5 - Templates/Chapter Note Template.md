---
<%*
let title = tp.file.title;
var book = title.slice(0,-13);
var chapter = title.slice(-2);
chapter = Number(chapter);
-%>
created: <% tp.file.creation_date() %>
title:
tags:
  - chapter
topics:
book: "[[<%* tR += `${book}` %>]]"
chapter: <%* tR += `${chapter}` %>
description:
date: <% tp.file.creation_date() %>
---

> [!summary]
> `INPUT[textArea:description]`

```meta-bind-button
label: Return to Book
icon: book-marked
style: default
actions:
  - type: open
    link: <%* tR += `${book}` %>
    newTab: false
```

---
## Notes

## Questions

## Quotes

---

```meta-bind-button
label: Return to Book
icon: book-marked
style: default
actions:
  - type: open
    link: <%* tR += `${book}` %>
    newTab: false
```
