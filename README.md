This is an example of how I set up a custom writing environment in Obsidian.

It uses the following plugins:

- Templater
- Kanban (For the project view)
- Meta Bind
- Typewriter Mode
- Enhancing Export (Optional, for export)
- Dataview (Need it for inline data that won't work with Bases)
- Spellcheck Toggler
- And a custom plugin I haven't released yet called Wordcount Property, which does what it says.

It uses a few custom templates that are the heart of the system.
- Writing Template - this is the important one, and the most complex. It applies different templates depending on which kanban list a note is generated from.
- Writing Project Template - creates the custom kanban views for writing projects
- New Draft Template - gets inserted into the project kanban to create a new draft list
- Scene Template
- Character Template
- Writing Planning Template (optional)

It uses two snippets
- writing_style.css - this makes the scene view an attractive dark on light page that draws your attention to it and helps to differentiate the writing pages from other note pages. It allows for single line paragraph separation with indentation. It embeds the [IaWriter Duo font](https://ia.net/topics/in-search-of-the-perfect-writing-font) which is one of the best writing fonts out there. Horizontal lines become three dots. Line lengths are capped for easier reading. It's great
- hide_properties.css does just that, It's optional. Hover over the property title to see them. Helps you to focus on the text.

