---
<%*
let title = tp.file.title;
// Parse the file name: <author> - <title> - <about>
let parts = title.split(" - ");
let author = parts[0] || "";
let sourceTitle = parts.slice(1, -1).join(" - ") || "";
let about = parts[parts.length - 1] || "";

// Quote & escape author for YAML
const escapedAuthor = `"${author.replace(/"/g, '\\"')}"`;
-%>
created: <% tp.file.creation_date() %>
tags:
  - atomic
aliases:
  - <%* tR += about %>
topics:
authors:
  - <%* tR += escapedAuthor %>
title: <%* tR += sourceTitle %>
parent:
chapter:
episode:
SeeAlso:
---

# <%* tR += about %>