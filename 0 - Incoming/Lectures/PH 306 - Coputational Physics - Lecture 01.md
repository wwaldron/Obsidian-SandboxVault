---
created: 2026-05-12 13:04
modified: 2026-05-12 13:04
tags:
  - lecture
topics:
instructor:
  - "null"
course: "[[PH 306 - Coputational Physics]]"
lecture: 1
date: 2026-05-12 13:04
summary:
---

> [!summary]
> `INPUT[textArea:summary]`

```meta-bind-button
label: Return to Course
icon: notebook
style: default
actions:
  - type: open
    link: PH 306 - Coputational Physics
    newTab: false
```

Lecture Date: `INPUT[dateTime:date]`

---

## Atomic Notes

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

## Notes

## Questions

### Pre-Lecture Questions

### Questions from Lecture

### Post-Lecture Questions

## Quotes

## Scripture References

## Tasks

- [ ]

---

```meta-bind-button
label: Return to Course
icon: notebook
style: default
actions:
  - type: open
    link: PH 306 - Coputational Physics
    newTab: false
```
