---
aliases: ["<% tp.file.title %>"]
---
<%*
firstDayOfThisMonth = tp.date.now("YYYY-MM-DD", 0, tp.file.title + "-01", "YYYY-MM-DD")
quarter = tp.date.now("YYYY", 0, firstDayOfThisMonth) + "-Q" + tp.date.now("Q", 0, firstDayOfThisMonth)
%>
Quarter [[<% quarter %>]]
## Summary

## Details

<%*
weeks = [...Array(6).keys()].map(
   offset => tp.date.weekday("YYYY-MM-DD", 1 + offset * 7, firstDayOfThisMonth, "YYYY-MM-DD") + "-to-" + tp.date.weekday("YYYY-MM-DD",  5 + offset * 7, firstDayOfThisMonth, "YYYY-MM-DD")  
)
%>

**Important: there are more lines than needed. Remove the extra lines**
- [[<% weeks[0] %>]]: ![[<% weeks[0] %>#Summary]]
- [[<% weeks[1] %>]]: ![[<% weeks[1] %>#Summary]]
- [[<% weeks[2] %>]]: ![[<% weeks[2] %>#Summary]]
- [[<% weeks[3] %>]]: ![[<% weeks[3] %>#Summary]]
- [[<% weeks[4] %>]]: ![[<% weeks[4] %>#Summary]]
- [[<% weeks[5] %>]]: ![[<% weeks[5] %>#Summary]]