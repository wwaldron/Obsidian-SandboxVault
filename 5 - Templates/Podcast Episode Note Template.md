---
<%*
let title = tp.file.title;
var series = title.slice(0, -21);
var episode = Number(title.slice(-2));

// Collect hosts from podcast series frontmatter
let hosts = [];
const seriesFile = tp.file.find_tfile(series);
if (seriesFile) {
  const fm = app.metadataCache.getFileCache(seriesFile)?.frontmatter;
  if (fm && fm.hosts !== undefined) {
    hosts = Array.isArray(fm.hosts) ? fm.hosts : [fm.hosts];
  }
}

// Quote & escape each item (always)
const blockLines = (hosts.length ? hosts : [""]).map(s =>
  `  - "${String(s).replace(/"/g,'\\"')}"`
).join("\n");
-%>
created: <% tp.file.creation_date() %>
modified: <% tp.file.last_modified_date() %>
published:
title:
tags:
  - podcasts
topics:
hosts:
<%* tR += blockLines %>
series: "[[<%* tR += `${series}` %>]]"
episode: <%* tR += `${episode}` %>
date: <% tp.file.creation_date() %>
summary:
---

> [!summary]
> `INPUT[textArea:summary]`

Published: `INPUT[date:published]`

```meta-bind-button
label: Return to Podcast Series
icon: podcast
style: default
actions:
  - type: open
    link: <%* tR += `${series}` %>
    newTab: false
```

```meta-bind-button
label: Open Podcast
icon: podcast
style: primary
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: ""
hidden: false
actions:
  - type: open
    link: ""
    newTab: true

```

---
## Notes

### Personal Notes

### Snipd Notes

## Questions

## Quotes

## Scripture References

## Tasks

- [ ]

---

```meta-bind-button
label: Return to Podcast Series
icon: podcast
style: default
actions:
  - type: open
    link: <%* tR += `${series}` %>
    newTab: false
```