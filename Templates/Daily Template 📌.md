---
aliases: [{{date:YYYY-MM-DD}}]
---

# Daily {{date:YYYY-MM-DD dddd}}
[[Daily <% tp.date.now("YYYY-MM-DD dddd", -1) %>| Previous day ⬅]]   • 📅 <% tp.date.now("dddd, DD MMMM YYYY") %>•  [[Daily <% tp.date.now("YYYY-MM-DD dddd", +1) %>|➡ Following day]]   • [[Weekly <% tp.date.now("YYYY[-w]WW", 0) %>|week <% tp.date.now("WW", 0) %>|]] 

## Work Log
- …





## Activity
### Modified
```dataview  
TABLE
	length(rows.file.name) as numfiles ,
	join(rows.file.link, ", ") as files
FROM "/"  
WHERE 
		file.mday.day = {{date:DD}}
	AND file.mday.month = {{date:MM}}
	AND file.mday.year = {{date:YYYY}}
FLATTEN
	dateformat(file.mtime, "HH:mm") as "Hour"
GROUP BY Hour
SORT Hour desc  
```

### Created
```dataview  
List
FROM "/"  
WHERE 
		file.cday.day = {{date:DD}}
	AND file.cday.month = {{date:MM}}
	AND file.cday.year = {{date:yyyy}}
```
