[[Journal/Daily/<%tp.date.now("YYYY-MM-DD", -1,tp.file.title,"YYYY-MM-DD")%> | Yesterday]] <-> [[Journal/Daily/<%tp.date.now("YYYY-MM-DD",1,tp.file.title,"YYYY-MM-DD")%> | Tomorrow]]
Week Summary: [[<%moment(tp.file.title).format("gggg-[W]ww")%>]]

# Este dia

```dataview
table without id
	file.link AS "ID",
	solicitante AS "Solicitante",
	numero AS "Numero",
	tags AS "Tags",
	choice(completado,"✔️","❌") AS "Check"
from "Journal/Daily"
where fileClass="Tickets" and contains(file.name,"<%tp.date.now("YYYY-MM-DD")%>") and fileClass="Tickets"
sort file.name DESC
```

[[<% tp.date.now("YYYY-MM-DD", -1) %>]] | [[<% tp.date.now("YYYY-MM-DD", 1) %>]]