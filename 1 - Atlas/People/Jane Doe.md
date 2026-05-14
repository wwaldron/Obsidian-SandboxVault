---
parent:
  - "[[People MoC]]"
  - "[[Student MoC]]"
tags:
  - person
  - student
first-name: Jane
middle-name:
last-name: Doe
personMet: true
aliases:
birthday:
source:
title:
skills:
organization:
undergraduate-school:
masters-school:
doctorate-school:
currentStudent: true
studentLevel: PhD
advisor: Me
url:
email:
phone:
address:
city:
state:
country:
zip:
discord-id:
facebook-id:
github-id:
instagram-id:
linkedin-id:
medium-id:
reddit-id:
twitter-id:
youtube-id:
zoom-id:
exampleProperty: "[[John Doe]]"
---

# Jane Doe

Current Student: `INPUT[toggle(defaultValue(true)):currentStudent]`

Student Level: `INPUT[inlineSelect(option(Undergraduate), option(Masters), option(PhD), option(Post-Doc), option(Graduated), defaultValue(Undergraduate)):studentLevel]`

Student's Advisor: `INPUT[text(defaultValue(Me)):advisor]`

## Bio

## References

## People

## Interests

## Interactions

```base
filters:
  and:
    - file.links.contains(this.file)
    - '!file.path.startsWith("5 - Templates")'
properties:
  file.name:
    displayName: Meeting File Name
  file.ctime:
    displayName: Date Created
  note.summary:
    displayName: Summary
views:
  - type: table
    name: Meetings Table
    filters:
      and:
        - file.name.lower().contains("Meeting")
    order:
      - file.name
      - file.ctime
      - summary
    sort:
      - property: file.ctime
        direction: DESC
    columnSize:
      file.ctime: 165
    rowHeight: medium
  - type: table
    name: Emails Table
    filters:
      and:
        - file.name.lower().contains("Email")
    order:
      - file.name
      - file.ctime
      - summary
    sort:
      - property: file.ctime
        direction: DESC
    columnSize:
      file.ctime: 165
    rowHeight: medium

```

## Notes
