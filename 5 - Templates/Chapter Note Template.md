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

### Atomic Notes

```meta-bind-button
label: Create New Atomic Note
icon: atom
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: Creates a new atomic note.
id: ""
hidden: false
actions:
  - type: runTemplaterFile
    templateFile: 5 - Templates/Atomic Note Trigger.md
```

```base
filters:
  and:
    - parent.contains(this.file.name)
    - file.tags.contains("atomic")
formulas:
  Title Link: file.asLink(aliases[0])
properties:
  note.about:
    displayName: About
  note.created:
    displayName: Created
  note.topics:
    displayName: Topics
views:
  - type: table
    name: Table
    order:
      - formula.Title Link
      - created
      - topics
    sort:
      - property: created
        direction: DESC
    columnSize:
      formula.Title Link: 300
      note.created: 150
```

### Text Notes

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
