---
aliases: []
tags:  []
type: project
project: Project01
status: wip
industry: some-industry
cdate: 2022-03-20 12:30 
mdate: Sunday 20th March 2022 12:37:44 
---


# Status
completion::  My-First-Meeting

# Description

# Meetings
List of meeting carried out.


```dataview 
TABLE
sdate as "Date" 
FROM "Projects" 
WHERE type = "meeting" AND
project = [[]].project
```


