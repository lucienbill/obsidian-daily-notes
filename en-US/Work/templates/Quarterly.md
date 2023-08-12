---
<%* quarter = tp.date.now("YYYY") + "-Q" + tp.date.now("Q") %>
aliases: ["<% quarter %>"]
---
Year [[<% tp.date.now("YYYY") %>-FY]]
## Summary

## Details
<%*
months = [...Array(3).keys()].map(
	offset => moment(moment.now()).add(offset-2, 'months').format('YYYY-MM')
)
%>
- [[<% months[0] %>]]: ![[<% months[0] %>#Summary]]
- [[<% months[1] %>]]: ![[<% months[1] %>#Summary]]
- [[<% months[2] %>]]: ![[<% months[2] %>#Summary]]