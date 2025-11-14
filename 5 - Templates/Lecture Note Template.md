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
