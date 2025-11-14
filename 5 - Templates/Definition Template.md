---
<%*
defName = await tp.system.prompt("What word are you defining?", "", true, false)
await tp.file.move("1 - Atlas/Definitions/" + defName)
-%>
def-type: atomic
source:
date: <% tp.date.now("YYYY-MM-DDTHH:mm") %>
aliases:
---
