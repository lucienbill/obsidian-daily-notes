---
<%* 
week = tp.file.title
%>
aliases: ["<% week %>"]
---
Month [[<% week.substr(0,7) %>]]
## Summary

## Details

<%* 
firstDayOfThisweek = tp.date.now("YYYY-MM-DD", 0, week.substr(0,10), "YYYY-MM-DD")
%>
- [[<% tp.date.weekday("YYYY-MM-DD", 1, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 1, firstDayOfThisweek) %>#Summary]]
- [[<% tp.date.weekday("YYYY-MM-DD", 2, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 2, firstDayOfThisweek) %>#Summary]]
- [[<% tp.date.weekday("YYYY-MM-DD", 3, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 3, firstDayOfThisweek) %>#Summary]]
- [[<% tp.date.weekday("YYYY-MM-DD", 4, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 4, firstDayOfThisweek) %>#Summary]]
- [[<% tp.date.weekday("YYYY-MM-DD", 5, firstDayOfThisweek) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 5, firstDayOfThisweek) %>#Summary]]