---
<%*
name = await tp.system.prompt("What is this person's name?", "", true, false)
-%>
<% await tp.file.move("1 - Atlas/People/" + name) -%>
parent:
  - "[[People MoC]]"
tags:
  - person
first-name: <% name.split(" ")[0] %>
middle-name:
last-name: <% name.split(" ").slice(-1) %>
personMet: false
aliases:
birthday:
source:
title:
skills:
organization:
undergraduate-school:
masters-school:
doctorate-school:
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
---

# <% name %>

Person Met Toggle: `INPUT[toggle:personMet]`

<% name %>'s Birthday: `INPUT[date:birthday]`

## Bio

## Quotes

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
