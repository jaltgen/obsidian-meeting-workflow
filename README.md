# obsidian-meeting-workflow

## What does it do.

This workflow helps to easily create meeting-minutes for project MOCs (I prefer to call them *dashboards*).


https://user-images.githubusercontent.com/517885/159161602-6872c3e8-0918-45d5-81c3-b33835af34f7.mp4



## Why does it do it - Use-Case.

My usecase is to quickly be able to create project-related meeting-minutes so I can always jot down notes with minimal effort if colleagues or clients crash-call me. This increases the **security of my knowledge about project work**, facilitates **better visibility of communications** by sharing meeting minutes, and also makes it easier to **hold stakeholders responsible** by being able to document who attended what meeting when where more reliably.

# Requirements

## Plugins

- [Templater](https://github.com/SilentVoid13/Templater) - absolutely amazing plugin 😍
- [Dataview](https://github.com/blacksmithgu/obsidian-dataview) - just as amazing as Templater 🎉

# What's in the Bag 🥓

The demo vault (zip) includes a basic structure. It works by having the *new-meeting* template keyed to **ALT+N**. The logic is such that it pulls the *project* frontmatter variable from the *parent Tfile* and sets it in the new file like so:

~~~ javascript
// set frontmatter project variable according to parent
let parent_tfile = tp.config.active_file;
let parent_cache = app.metadataCache.getFileCache(parent_tfile);
let project = parent_cache.frontmatter["project"];
~~~

Then it *queries for a filename* and concatenates the result with my preferred filenaming scheme. This way, the plain-text file stays useful, as also the filename contains a date and project-ID. This can of course be changed really easily. 

**OH**. And it also moves the file to the project-subfolder for tidyness.

~~~ javascript
// create new filename
let variablename = await tp.system.prompt("Note Title");
let path = "/Projects/"+project+"/"+tp.date.now("YYYYMMDD")+""+project+"_"+variable_name;

//move file
await tp.file.move(path);
~~~

# What's Next? 🤷‍♂️

- 💥 creating a button to trigger the meeting-note creation
- 💥 making the move action relative to the parent-file location and not hard-coded

Really, I have like 1000 ideas of how this can help me, as I have a few data structures that are hierarchical within my main vault, such as Author>Source relationships. I realize that strict parent-child systems aren't helpful to broad-strokes thinking, but my mind is going the way of thinking about this like a database (in this case for meeting minutes, or lists of reading material and authors). I'll think about where this might go in the future.

# Contact 📨

You can reach out to me here or find me on the obsidian discord.
