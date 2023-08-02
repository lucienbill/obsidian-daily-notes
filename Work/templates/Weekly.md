---
<%* 
week = tp.date.weekday("YYYY-MM-DD", 1) + "-to-" + tp.date.weekday("YYYY-MM-DD", 5)
%>
aliases: ["Work/Tracking/<% tp.date.now("YYYY") %>/<% tp.date.now("MM") %>/<% week %>"|"<% week %>"]
---
Month [[Work/Tracking/<% tp.date.now("YYYY-MM") %>|<% tp.date.now("YYYY-MM") %>]]
## Summary

## Details

- [[Work/Tracking/Daily/<% tp.date.weekday("YYYY-MM-DD", 1) %>|<% tp.date.weekday("YYYY-MM-DD", 1) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 1) %>#Summary]]
- [[Work/Tracking/Daily/<% tp.date.weekday("YYYY-MM-DD", 2) %>|<% tp.date.weekday("YYYY-MM-DD", 2) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 2) %>#Summary]]
- [[Work/Tracking/Daily/<% tp.date.weekday("YYYY-MM-DD", 3) %>|<% tp.date.weekday("YYYY-MM-DD", 3) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 3) %>#Summary]]
- [[Work/Tracking/Daily/<% tp.date.weekday("YYYY-MM-DD", 4) %>|<% tp.date.weekday("YYYY-MM-DD", 4) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 4) %>#Summary]]
- [[Work/Tracking/Daily/<% tp.date.weekday("YYYY-MM-DD", 5) %>|<% tp.date.weekday("YYYY-MM-DD", 5) %>]]: ![[<% tp.date.weekday("YYYY-MM-DD", 5) %>#Summary]]