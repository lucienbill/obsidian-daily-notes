---
aliases: ["<% tp.file.title %>"]
---
<%*
firstDayOfThisMonth = tp.date.now("YYYY-MM-DD", 0, tp.file.title + "-01", "YYYY-MM-DD")
quarter = tp.date.now("YYYY", 0, firstDayOfThisMonth) + "-Q" + tp.date.now("Q", 0, firstDayOfThisMonth)
%>
Trimestre [[<% quarter %>]]
## Résumé

## Détails

<%*
weeks = [...Array(6).keys()].map(
   offset => tp.date.weekday("YYYY-MM-DD", 1 + offset * 7, firstDayOfThisMonth, "YYYY-MM-DD") + "-to-" + tp.date.weekday("YYYY-MM-DD",  5 + offset * 7, firstDayOfThisMonth, "YYYY-MM-DD")  
)
%>

**Important: Il y a plus de lignes que nécessaire. Enlevez les lignes superflues**
- [[<% weeks[0] %>]]: ![[<% weeks[0] %>#Résumé]]
- [[<% weeks[1] %>]]: ![[<% weeks[1] %>#Résumé]]
- [[<% weeks[2] %>]]: ![[<% weeks[2] %>#Résumé]]
- [[<% weeks[3] %>]]: ![[<% weeks[3] %>#Résumé]]
- [[<% weeks[4] %>]]: ![[<% weeks[4] %>#Résumé]]
- [[<% weeks[5] %>]]: ![[<% weeks[5] %>#Résumé]]