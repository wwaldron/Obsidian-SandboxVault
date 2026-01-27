---
parent:
podcast:
hosts:
aliases: []
description:
---

> [!summary] Series Summary
> `INPUT[textArea:description]`

## Episodes

```meta-bind-button
label: Create New Podcast Episode Note
icon: podcast
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: Creates a new podcast note in the Podcasts subdirectory.
id: ""
hidden: false
actions:
  - type: runTemplaterFile
    templateFile: 5 - Templates/Podcast Episode Note Trigger.md

```

```base
formulas:
  Title Link: file.asLink(aliases[0])
properties:
  note.topics:
    displayName: Topics
  note.published:
    displayName: Date Published
  note.episode:
    displayName: Ep
views:
  - type: table
    name: Episode List
    filters:
      and:
        - series == this.file
    order:
      - episode
      - published
      - formula.Title Link
      - topics
    sort:
      - property: episode
        direction: ASC
    columnSize: {}
```

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
    - parent == this.file
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
