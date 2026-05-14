---
date: <% tp.date.now("YYYY-MM-DD") %>
year: <% tp.date.now("YYYY") %>
tags:
  - PeriodicNote/Daily
topics:
aliases:
parent:
  - "[[Daily Notes.base]]"
---

## Tasks Due Soon

```tasks
not done
is not blocked
(due on or before <% tp.date.now("YYYY-MM-DD", 5) %>) OR (scheduled on or before <% tp.date.now("YYYY-MM-DD") %>)
hide created date
hide tags
hide recurrence rule
hide id
hide depends on
sort by urgency
```

## Notes Made or Modified Today

```base
filters:
  and:
    - file.name != this.file.name
formulas:
  File Links List: file.links.unique().map([value.asFile(),", "]).flat().slice(0,-1)
properties:
  file.name:
    displayName: File Name
  file.links:
    displayName: File Links
  file.tags:
    displayName: Tags
views:
  - type: list
    name: Created Today
    filters:
      and:
        - file.ctime == "<% tp.date.now('YYYY-MM-DD') %>"
    order:
      - file.name
      - formula.File Links List
      - file.tags
    sort:
      - property: file.ctime
        direction: DESC
    indentProperties: true
  - type: list
    name: Modified Today
    filters:
      and:
        - file.mtime == "<% tp.date.now('YYYY-MM-DD') %>"
    order:
      - file.name
      - formula.File Links List
      - file.tags
    sort:
      - property: file.mtime
        direction: DESC
    limit: 5
    indentProperties: true

```

## New Tasks

## Quick Notes

## Meetings

## Journaling Notes
