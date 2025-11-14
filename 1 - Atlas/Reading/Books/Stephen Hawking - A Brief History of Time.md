---
title: A Brief History of Time
aliases:
  - A Brief History of Time
authors: Stephen Hawking
SortName: Stephen Hawking
series:
seriesnumber:
rating:
readdates.started:
readdates.finished:
shelf: To Read
list:
publisher: Bantam
published: 2011-05-04
pages: 226
isbn: 055389692X
cover: https://books.google.com/books/publisher/content/images/frontcover/oZhagX6UWOMC?fife=w600-h900&source=gbs_api
dateCreated: 2025-11-14
format:
recommendedBy:
loanedTo:
bookReturnDate:
previousLoans:
parent:
  - "[[Books.base]]"
---

# Stephen Hawking - A Brief History of Time

`VIEW[{cover}][image]`

Current Shelf: `INPUT[inlineSelect(title(Current Shelf), option(To Read), option(Interested), option(Recommended), option(Reading), option(Finished), option(Stopped), option(Archived)):shelf]`

## A Brief History of Time

### Description

#1 NEW YORK TIMES BESTSELLER A landmark volume in science writing by one of the great minds of our time, Stephen Hawking's book explores such profound questions as: How did the universe begin—and what made its start possible? Does time always flow forward? Is the universe unending—or are there boundaries? Are there other dimensions in space? What will happen when it all ends? Told in language we all can understand, A Brief History of Time plunges into the exotic realms of black holes and quarks, of antimatter and "arrows of time," of the big bang and a bigger God—where the possibilities are wondrous and unexpected. With exciting images and profound imagination, Stephen Hawking brings us closer to the ultimate secrets at the very heart of creation.

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
