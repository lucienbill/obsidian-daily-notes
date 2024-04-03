---
<%* quarter = tp.file.title %>
aliases: ["<% quarter %>"]
---
<%*
thisQuarter = parseInt(tp.file.title.substr(tp.file.title.length - 1))
thisYear = tp.file.title.substr(0,4)
refDateStr = "" + thisYear + "-" + (1 + (thisQuarter - 1) * 3 ) + "-01"
firstDayOfThisQuarter = tp.date.now("YYYY-MM-DD", 0, refDateStr, "YYYY-MM-DD")
%>
Année [[<% thisYear%>-FY]]
## Résumé

## Détails
<%*
months = [...Array(3).keys()].map(
	offset => tp.date.now("YYYY-MM", "P+" + offset + "M", refDateStr)
)
%>
- [[<% months[0] %>]]: ![[<% months[0] %>#Résumé]]
- [[<% months[1] %>]]: ![[<% months[1] %>#Résumé]]
- [[<% months[2] %>]]: ![[<% months[2] %>#Résumé]]