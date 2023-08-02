# Obsidian Daily Notes
## What's that thing for (description)?
There are a few questions my brain struggles to answer:
- What have I done yesterday? And last week? Last month?
- Where did I stop yesterday? What was my plan?

Thankfully I take notes: there are the persistent memory that I don't naturally have.
For years I wrote things in a mostly unordered fashion in many unsaved tabs in NotePad++.
While better than nothing, it has its limitations.

I recently discovered [this article](https://v5.chriskrycho.com/journal/writing-down-what-i-do-in-obsidian/) by Chris Krycho: "Writing Down What I Do—In Obsidian".

This repository is my own version of his system:
- The structure is looser (simpler for me to leverage)
- It makes use of the Templater plugin to automate some naming and links

## Requirements
TODO; Obsidian + Templater (community pluggin)
## Configuration
Copy the templates from `{this repo}/Work/templates` into `{your Obsidian Vault}/Work/templates`

Then configure Obisidian:
- Obsidian > Settings > Core plugins (Options) > Templates = **Off**
- Obsidian > Settings > Daily notes (Core plugins) > New file location = `Work/Tracking/Daily`
- Obsidian > Settings > Daily notes (Core plugins) > Template file location = `Work/templates/Daily`
- Obsidian > Settings > Templater (Community pluggin) > Template folder location = `Work/templates`
- Obsidian > Settings > Templater (Community pluggin) > Trigger Templater on new file location = **On**

Then exit the Settings, and click on "Open today's daily note" (by default it should be a calendar icon on the left bar).
They "Daily" template will be automatically executed on your daily note.

Other templates will need to be manually executed on your selected file from the "Templater" icon (it looks like `<%`)

Note: depending on your system, the templates might consider that your week start on Sunday.
In France on my French computer, work weeks are configured "from Monday to Friday".
You might need to fiddle with all instances of `tp.date.weekday` in the templates, and with the Monthly template

## How do I use it
Everyday, I write stuff:
- What I plan to do
- What I learned
- What I achieved
- What I struggled with
- What my plan for the future (next day or other period) is

At the end of the day, under `## Summary` I summarise the most important stuff.

At the end of the week, I open the weekly note, take a look on the combined summaries of each day, and I summarise my week.
Then my month, quarter, year...

It helps me with keeping track of what I have done and what I plan to do, and can help with HR review.
It can help with writting a [brag document](https://jvns.ca/blog/brag-documents/).


## Contributions
TODO;
TL;DR=please contribute in whatever form suits you. I read the issues and the PR
