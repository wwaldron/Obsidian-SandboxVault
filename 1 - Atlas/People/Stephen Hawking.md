---
parent:
  - "[[People MoC]]"
tags:
  - person
first-name: Stephen
middle-name:
last-name: Hawking
personMet: false
aliases: []
birthday: 1942-01-08
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

# Stephen Hawking

Person Met Toggle: `INPUT[toggle:personMet]`

Stephen Hawking's Birthday: `INPUT[date:birthday]`

## Bio

### [Wikipedia](https://en.wikipedia.org/wiki/Stephen_Hawking)

**Stephen William Hawking** (8 January 1942 - 14 March 2018) was an English theoretical [astrophysicist](https://en.wikipedia.org/wiki/Astrophysics "Astrophysics"), [cosmologist](https://en.wikipedia.org/wiki/Cosmologist "Cosmologist"), and author who was director of research at the [Centre for Theoretical Cosmology](https://en.wikipedia.org/wiki/Centre_for_Theoretical_Cosmology "Centre for Theoretical Cosmology") at the [University of Cambridge](https://en.wikipedia.org/wiki/University_of_Cambridge "University of Cambridge"). Between 1979 and 2009, he was the [Lucasian Professor of Mathematics](https://en.wikipedia.org/wiki/Lucasian_Professor_of_Mathematics "Lucasian Professor of Mathematics") at Cambridge, widely viewed as one of the most prestigious academic posts in the world.

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
