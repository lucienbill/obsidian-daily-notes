---
aliases: ["<% tp.file.title %>"]
---
<%* 
filedate = tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD")
week = tp.date.weekday("YYYY-MM-DD", 1, filedate, "YYYY-MM-DD") + "-to-" + tp.date.weekday("YYYY-MM-DD", 5, filedate, "YYYY-MM-DD") %>
Week [[<% week %>]]

## Summary

## Details
