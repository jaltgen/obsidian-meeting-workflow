


<%*  
// set frontmatter project variable according to parent  
let parent_tfile = tp.config.active_file;  
let parent_cache = app.metadataCache.getFileCache(parent_tfile);  
let project = parent_cache.frontmatter["project"];

// create new filename  
let variable_name = await tp.system.prompt("Note Title");  
let path = "/Projects/"+project+"/"+tp.date.now("YYYYMMDD")+"_"+project+"_"+variable_name;

//move file  
await tp.file.move(path);

%>

---
aliases: []
type: meeting
project: <% await project %>
cdate: <% tp.file.creation_date() %> 
mdate: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %> 
---

# Attendees
- [[Person One]]
- [[Person Two]]
...

# Agenda
What is plannend.

# Notes
What happend

# Outcome
Next steps...