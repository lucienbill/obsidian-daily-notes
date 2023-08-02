---
aliases: ["Work/Tracking/<% tp.date.now("YYYY") %>/<% tp.date.now("YYYY-MM") %>"|"<% tp.date.now("YYYY-MM") %>"]
---
<%* quarter = tp.date.now("YYYY") + "-Q" + tp.date.now("Q") %>
Quarter [[Work/Tracking/<% quarter %>|<% quarter %>]]
## Summary

## Details

<%*
weeks = [...Array(6).keys()].map(
   offset => moment().startOf('month').day("Monday").add(parseInt(offset*7), 'd').format('YYYY-MM-DD') + "-to-" + moment().startOf('month').day("Monday").add(parseInt(offset*7)+4, 'd').format('YYYY-MM-DD')
)
%>

**Important: there are more lines than needed. Remove the extra lines**
- [[Work/Tracking/<% weeks[0] %>|<% weeks[0] %>]]: ![[<% weeks[0] %>#Summary]]
- [[Work/Tracking/<% weeks[1] %>|<% weeks[1] %>]]: ![[<% weeks[1] %>#Summary]]
- [[Work/Tracking/<% weeks[2] %>|<% weeks[2] %>]]: ![[<% weeks[2] %>#Summary]]
- [[Work/Tracking/<% weeks[3] %>|<% weeks[3] %>]]: ![[<% weeks[3] %>#Summary]]
- [[Work/Tracking/<% weeks[4] %>|<% weeks[4] %>]]: ![[<% weeks[4] %>#Summary]]
- [[Work/Tracking/<% weeks[5] %>|<% weeks[5] %>]]: ![[<% weeks[5] %>#Summary]]