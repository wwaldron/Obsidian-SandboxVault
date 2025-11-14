---
date: <% tp.date.now("YYYY-MM-DD") %>
year: <% tp.date.now("YYYY") %>
tags:
  - PeriodicNote/Daily
topics:
aliases:
parent:
  - "[[Daily Notes Base.base]]"
---

## Tasks Due Soon

```tasks
not done
((due on or before <% tp.date.now("YYYY-MM-DD", 3) %>) AND (due on or after <% tp.date.now("YYYY-MM-DD", -1) %>)) OR (scheduled on <% tp.date.now("YYYY-MM-DD") %>)
hide tags
sort by due
sort by priority
group by function task.tags.sort().join(", ")
```

## New Tasks

- [ ] 

## Quick Notes

- {Place Quick Notes Here}

## Meetings

## Journaling Notes
