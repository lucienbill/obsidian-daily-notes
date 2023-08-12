---
aliases: ["<% tp.date.now("YYYY-MM") %>"]
---
<%* quarter = tp.date.now("YYYY") + "-Q" + tp.date.now("Q") %>
Trimestre [[<% quarter %>]]
## Résumé

## Détails

<%*
weeks = [...Array(6).keys()].map(
   offset => moment().startOf('month').day("Monday").add(parseInt(offset*7), 'd').format('YYYY-MM-DD') + "-to-" + moment().startOf('month').day("Monday").add(parseInt(offset*7)+4, 'd').format('YYYY-MM-DD')
)
%>

**Important: Il y a plus de lignes que nécessaire. Enlevez les lignes superflues**
- [[<% weeks[0] %>]]: ![[<% weeks[0] %>#Résumé]]
- [[<% weeks[1] %>]]: ![[<% weeks[1] %>#Résumé]]
- [[<% weeks[2] %>]]: ![[<% weeks[2] %>#Résumé]]
- [[<% weeks[3] %>]]: ![[<% weeks[3] %>#Résumé]]
- [[<% weeks[4] %>]]: ![[<% weeks[4] %>#Résumé]]
- [[<% weeks[5] %>]]: ![[<% weeks[5] %>#Résumé]]