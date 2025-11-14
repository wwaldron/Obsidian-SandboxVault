---
parent:
aliases: []
instructor:
description:
---

> [!summary] [Catalog Description]()
> `INPUT[textArea:description]`

## Semester
```dataviewjs
var a = moment("2025-01-01");
var b = moment("2025-12-31");

var n = moment()
var t = moment().startOf('day');

let q =  b.diff(a, 'days');
let p =  b.diff(t, 'days');
let r =  t.diff(a, 'days');

let h = n.diff(a, 'hours');
let i = b.diff(a, 'hours');

let html = `<progress style="height:10px;width:80%" value="`+h+`" max="`+i+`"></progress>`

if (r>0 && r<q) {
    html += `\n`+p+` Days Left of `+q+` Days\n`
    html += (h/i*100).toFixed(2)+`% Complete`
} else if (r==0) {
    html += `\nCourse Starts Today`
} else if (r==q) {
    html += `\nEnds today`
} else if (r>q) {
    html += `\nEnded `+-p+` Days Ago`
}else {
    html += `\n`+-r+` Days until Course Starts`
}

dv.paragraph(html)
```

### Reading List

### Syllabus

## Lectures

```meta-bind-button
label: Create New Lecture Note
icon: notebook-pen
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: Creates a new lecture note in the Lectures subdirectory.
id: ""
hidden: false
actions:
  - type: runTemplaterFile
    templateFile: 5 - Templates/Lecture Note Trigger.md

```

```base
formulas:
  Lectures: link(file.name, "Lecture " + lecture.toString())
properties:
  note.topics:
    displayName: Topics
  note.date:
    displayName: Date
views:
  - type: table
    name: Table
    filters:
      and:
        - course == this.file
    order:
      - formula.Lectures
      - date
      - topics
    sort:
      - property: lecture
        direction: ASC
    columnSize:
      note.date: 193

```