---
<%*
let title = tp.file.title;
var course = title.slice(0,-13);
var lecture = title.slice(-2);
lecture = Number(lecture);

// Collect instructors from course frontmatter
let instructors = [];
const courseFile = tp.file.find_tfile(course);
if (courseFile) {
  const fm = app.metadataCache.getFileCache(courseFile)?.frontmatter;
  if (fm && fm.instructor !== undefined) {
    instructors = Array.isArray(fm.instructor) ? fm.instructor : [fm.instructor];
  }
}

// Quote & escape each item (always)
const blockLines = (instructors.length ? instructors : [""]).map(s =>
  `  - "${String(s).replace(/"/g,'\\"')}"`
).join("\n");
-%>
created: <% tp.file.creation_date() %>
modified: <% tp.file.last_modified_date() %>
tags:
  - lecture
topics:
instructor:
<%* tR += blockLines %>
course: "[[<%* tR += `${course}` %>]]"
lecture: <%* tR += `${lecture}` %>
date: <% tp.file.creation_date() %>
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
    link: <%* tR += `${course}` %>
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
    link: <%* tR += `${course}` %>
    newTab: false
```
