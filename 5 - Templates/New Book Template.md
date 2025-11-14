---
title: "{{title}}"
aliases: ["{{title}}"]
authors: {{authors}}
SortName: {{author}}
series:
seriesnumber:
rating:
readdates.started:
readdates.finished:
shelf: To Read
list:
publisher: {{publisher}}
published: {{publishDate}}
pages: {{totalPage}}
isbn: {{isbn10}}
cover: <%=book.coverUrl ? `https://books.google.com/books/publisher/content/images/frontcover/${[...book.coverUrl.split("&")[0].matchAll(/id.?(.*)/g)][0][1]}?fife=w600-h900&source=gbs_api` : ''%>
dateCreated: {{date}}
format:
recommendedBy:
loanedTo:
bookReturnDate:
previousLoans:
---

`VIEW[{cover}][image]`

Current Shelf: `INPUT[inlineSelect(title(Current Shelf), option(To Read), option(Interested), option(Recommended), option(Reading), option(Finished), option(Stopped), option(Archived)):shelf]`

## {{title}}

### Description

{{description}}

### Key Notes

#### Chapter Notes

```meta-bind-button
label: Create New Chapter Note
icon: notebook-pen
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: Creates a new lecture note in the Chapters subdirectory.
id: ""
hidden: false
actions:
  - type: runTemplaterFile
    templateFile: 5 - Templates/Chapter Note Trigger.md
```

```base
filters:
  and:
    - book == this.file
formulas:
  Title Link: file.asLink(title)
properties:
  file.name:
    displayName: File Name
  note.date:
    displayName: Date
  note.topics:
    displayName: Topics
  note.title:
    displayName: Title
  note.chapter:
    displayName: Chapter
views:
  - type: table
    name: Table
    order:
      - formula.Title Link
      - date
      - topics
    sort:
      - property: chapter
        direction: ASC
    columnSize:
      formula.Title Link: 200
      note.date: 200
```

### Review
