This is an example vault showing how I set up a custom writing environment in Obsidian. I hope it can serve as inspiration for people looking for ideas to setup or improve their writing environment in Obsidian. 

If you want to try it, I suggest downloading it and unzipping it, then use the "Open folder as vault" option in the vault manager. From there you can try it out and move it to your own vault if you like. Because it's not a plugin it's designed to be transparent and customizable, but be warned that some parts tie together and might not function right if separated. Also, some things will look different depending on the theme you use, and the writing-style.css snippet might have to be modified. In my own vault I've tested it with the [Minimal](https://github.com/kepano/obsidian-minimal) theme.

# Plugins

It uses the following community plugins:

- [Templater](https://github.com/SilentVoid13/Templater) - Essential for using the custom templates listed below.
- [Kanban](https://github.com/mgmeyers/obsidian-kanban) - When used in list view I've learned that a kanban board makes the perfect project overview. It's a highly customizable way to see everything related to a project in one place, and I've highjacked it's ability to apply a custom template to notes created from it to create my system.
- [Meta Bind](https://github.com/mProjectsCode/obsidian-meta-bind-plugin) - For the occasional button and field.
- [Typewriter Mode](https://github.com/davisriedel/obsidian-typewriter-mode) - Optional, but I like the typewriter scrolling feature which keeps the place where I'm writing at the center of the screen, closer to eye level. It's more feature-full than the other typewriter plugin.
- [Enhancing Export](https://github.com/mokeyish/obsidian-enhancing-export) - I would say it's optional, but you do what to send what you write out into the world, right? Copying and pasting markdown rarely works like you want it to.
- [Dataview](https://github.com/blacksmithgu/obsidian-dataview) - Used to track inline notes that I add to my writing to remind me to come back and fix something. Bases can't list inline properties.
- And a custom plugin I haven't released yet called Wordcount Property, which does what it says.

# Templates

It uses a few custom templates that are the heart of the system.
- Writing Project Template - Creates the custom kanban views for new writing projects
- Writing Template - This is the important one, and the most complex. This and the following templates are used internally by the kanban board and are not intended to be used separately This is called from any note you create from the kanban project page, and it applies different templates depending on which list the note is generated from. It moves them to matching sub folders and fills out some of the properties.
- New Draft Template - This gets inserted into the project kanban to create a new draft list.
- Scene Template - Notes created from a draft kanban list will have this template applied. The story title, draft number, and a link to the project file will be automatically added in the properties. It will make a guess at the chapter number, which can be edited if you want to track that for your own use. It includes the writing css class that I describe below. It has a property used by a plugin I made that will update with the word count when focus switched away from the note.
- Character Template - Notes created from the Character kanban list will have this template applied. I've added some properties that I use to help me flesh out a character, but those can be customized to suit the author.
- Writing Planning Template - Optional. This is just there because I wanted my planning notes to link back to the project page.

# Snippets

### writing_style.css

I spend a lot of time staring at a writing page, so I want it to be beautiful and functional. This snippet has been a work in project for years, though I will say that I'm no expert on css, so feel free to let me know if there's a better way to do some of this. 

It makes the writing area an attractive dark on light (not harsh black on white) page that draws your attention to it and helps to differentiate the writing pages from other note pages. It loosely approximates the printed page by limiting line width and allowing for single line paragraph separation with indentation. It embeds the [IaWriter Duo font](https://ia.net/topics/in-search-of-the-perfect-writing-font) which is the best writing font out there. Horizontal rules become centered three-dot separators. Internal links blend into the rest of the text until hovered over. 
### hide_properties.css

Optional, but I think it's nice to hide the properties on scene pages so you can focus on the text you're writing. Hover over the property title to see and edit them, or open the Properties tab. 

### hide_dataview_error.css

This just hides the dataview error boxes on the project page.

# History

I've used several writing programs over the years, including the popular Scrivener, but I always wanted something that was more customizable and integrated with my research notes. Obsidian had that, and at first the Longform plugin served as the framework for organizing my writing projects. Give it a try, you might like it! I found that over time Longform wasn't quite what I wanted (that, and it had persistent problems with losing my scene order on sync), so I set out to make my own ultimate writing environment. Through a few novel drafts and dozens of short stories, I've continued to tweak my system, eventually ending up with what you see here.


