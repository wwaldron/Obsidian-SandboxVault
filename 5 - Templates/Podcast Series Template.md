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
  Title Link: file.asLink(title)
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
