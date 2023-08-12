---
<%* quarter = tp.date.now("YYYY") + "-Q" + tp.date.now("Q") %>
aliases: ["<% quarter %>"]
---
Année [[<% tp.date.now("YYYY") %>-FY]]
## Résumé

## Détails
<%*
months = [...Array(3).keys()].map(
	offset => moment(moment.now()).add(offset-2, 'months').format('YYYY-MM')
)
%>
- [[<% months[0] %>]]: ![[<% months[0] %>#Résumé]]
- [[<% months[1] %>]]: ![[<% months[1] %>#Résumé]]
- [[<% months[2] %>]]: ![[<% months[2] %>#Résumé]]