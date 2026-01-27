---
<%*
// Variables

// Get File Name Details
let fileElements;
var authorName, workTitle;
fileElements = tp.file.title.split("-");
authorName = fileElements[0].trim();
workTitle = fileElements[1].trim();
-%>
authors:
  - "[[<% authorName %>]]"
SortName:
speaker:
title: <% workTitle %>
quote:
created: <% tp.file.creation_date("YYYY-MM-DD") %>
published:
context:
rating:
aliases:
tags:
  - atomic
topics:
parent:
  - "[[Quote MoC]]"
SeeAlso:
---

Quote Rating: `INPUT[slider(minValue(0), maxValue(5), stepSize(0.05), title(Rating), addLabels(true)):rating]` `VIEW[{rating}]`

> [!quote] `INPUT[inlineList(placeholder(Author/Speaker) ):authors]` `INPUT[text(placeholder(Work Title)):title]`
> 
> `INPUT[textArea:quote]`

^111111