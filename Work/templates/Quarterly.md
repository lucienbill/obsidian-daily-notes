---
<%* quarter = tp.date.now("YYYY") + "-Q" + tp.date.now("Q") %>
aliases: ["Work/Tracking/<% tp.date.now("YYYY") %>/<% quarter %>"|"<% quarter %>"]
---
Year [[Work/Tracking/<% tp.date.now("YYYY") %>-FY|<% tp.date.now("YYYY") %>-FY]]
## Summary

## Details
<%*
months = [...Array(3).keys()].map(
	offset => moment(moment.now()).add(offset-2, 'months').format('YYYY-MM')
)
%>
- [[Work/Tracking/<% months[0] %>|<% months[0] %>]]: ![[<% months[0] %>#Summary]]
- [[Work/Tracking/<% months[1] %>|<% months[1] %>]]: ![[<% months[1] %>#Summary]]
- [[Work/Tracking/<% months[2] %>|<% months[2] %>]]: ![[<% months[2] %>#Summary]]