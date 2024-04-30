---
creation date: <% tp.file.creation_date() %>
modification date: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
fileClass: Week
---
# <%moment(tp.file.title).startOf('isoWeek').format("MMMM DD")%> - <%moment(tp.file.title).endOf('isoWeek').format("MMM DD")%>

[[Journal/Weekly/<%moment(tp.file.title).subtract(1,'week').format("gggg-[W]ww")%> | ↺Previous Week]] | [[Journal/Weekly/<%moment(tp.file.title).add(1,'week').format("gggg-[W]ww")%> | ↻Next Week]]
# Overview

```dataview
table without id
	file.link AS "ID",
	solicitante AS "Solicitante",
	numero AS "Numero",
	articulo AS "Articulo",
	canal AS "Canal",
	estado AS "Estado",
	choice(completado,"✔️","❌") AS "Check"
from "Journal/Daily"
where week="<%moment(tp.file.title).format("gggg-[W]ww")%>"
sort file.name DESC
```

