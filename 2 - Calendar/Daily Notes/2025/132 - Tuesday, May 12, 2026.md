---
date: 2026-05-12
year: 2026
tags:
  - PeriodicNote/Daily
topics:
aliases: []
parent:
  - "[[Daily Notes Base.base]]"
---

# 132 - Tuesday, May 12, 2026

## Tasks Due Soon

```tasks
not done
is not blocked
(due on or before 2026-05-17) OR (scheduled on or before 2026-05-12)
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
        - file.ctime == "2026-05-12"
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
        - file.mtime == "2026-05-12"
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

- [ ] This is a Task 📅 2026-05-13 #ToDo/UAH

## Quick Notes

## Meetings

## Journaling Notes
