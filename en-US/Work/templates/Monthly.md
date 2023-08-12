---
aliases: ["<% tp.date.now("YYYY-MM") %>"]
---
<%* quarter = tp.date.now("YYYY") + "-Q" + tp.date.now("Q") %>
Quarter [[<% quarter %>]]
## Summary

## Details

<%*
weeks = [...Array(6).keys()].map(
   offset => moment().startOf('month').day("Monday").add(parseInt(offset*7), 'd').format('YYYY-MM-DD') + "-to-" + moment().startOf('month').day("Monday").add(parseInt(offset*7)+4, 'd').format('YYYY-MM-DD')
)
%>

**Important: there are more lines than needed. Remove the extra lines**
- [[<% weeks[0] %>]]: ![[<% weeks[0] %>#Summary]]
- [[<% weeks[1] %>]]: ![[<% weeks[1] %>#Summary]]
- [[<% weeks[2] %>]]: ![[<% weeks[2] %>#Summary]]
- [[<% weeks[3] %>]]: ![[<% weeks[3] %>#Summary]]
- [[<% weeks[4] %>]]: ![[<% weeks[4] %>#Summary]]
- [[<% weeks[5] %>]]: ![[<% weeks[5] %>#Summary]]