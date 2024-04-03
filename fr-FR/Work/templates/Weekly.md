---
<%* 
week = tp.file.title
%>
aliases: ["<% week %>"]
---
Mois [[<% week.substr(0,7) %>]]
## Résumé

## Détails
<%* 
firstDayOfThisweek = tp.date.now("YYYY-MM-DD", 0, week.substr(0,10), "YYYY-MM-DD")
%>

- [[<% tp.date.weekday("YYYY-MM-DD", 1, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 1, firstDayOfThisweek) %>#Résumé]]
- [[<% tp.date.weekday("YYYY-MM-DD", 2, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 2, firstDayOfThisweek) %>#Résumé]]
- [[<% tp.date.weekday("YYYY-MM-DD", 3, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 3, firstDayOfThisweek) %>#Résumé]]
- [[<% tp.date.weekday("YYYY-MM-DD", 4, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 4, firstDayOfThisweek) %>#Résumé]]
- [[<% tp.date.weekday("YYYY-MM-DD", 5, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 5, firstDayOfThisweek) %>#Résumé]]