This is an example vault showing how I set up a custom writing environment in Obsidian. I hope it can serve as inspiration for people looking for ideas to setup or improve their writing environment in Obsidian. 

It's not a plugin, but a combination of plugins, templates, and snippets that I use to create a productive, organized, and attractive writing environment. It can mostly be adapted to your own workflow, but some of the templates interoperate in a specific way that requires some explanation.

# Background

I always want to have access to metadata about the project while I write, information at a glance  about characters, timelines, planning, and research documents. I also want to be able to open a previous draft and reference it while I write the next one. I've used many programs for writing over the years, and I was always frustrated with the lack of customizability. While I found that flexibility in Obsidian, it lacked the finesse of a purpose built writing tool -- but of course that's something that can be fixed!

After years of experimenting in Obsidian, including using the Longform plugin, I realized that a Kanban board, specifically one set to "list" view, made the perfect side-panel. It's incredibly flexible and I can customize it for each project, turning it into a gathering point for all project related notes and links, and using the hover preview feature to quickly find the info I needed without leaving the page. It's far better than a Base table because you can drag items around to reorganize scene order, etc. The only thing it needed was a way to organize drafts, so I spent some time making custom templates to handle that. 

# The System

The Kanban plugin can apply a custom template to notes created from cards. I made a template that takes it further by figuring out which list the card was in and applying a separate template depending on if it came from a Draft list, a Character list, etc. I added a dataview to each draft list that displays the total word count and any inline "todo" notes I've added to my chapters. In order to simplify creating these draft lists I added a button via Metabind that adds them to the project. 

So the system looks like this:
1.  The Writing Projects Homepage has a button that creates a new project note from the "Writing Project Template", which is a custom Kanban board with all features and settings already in place. 
2. From there you can hit the button to create a New Draft, which will insert a new list using the "New Draft Template". 
3. You add scenes, characters, and other notes by adding cards to the correct list and using the "New note from card" option from the card context menu (three dots). Those automatically have different templates applied based on which list it's in.

If you want to try it, I suggest downloading it and unzipping it, then use the "Open folder as vault" option in the vault manager. From there you can try it out and move it to your own vault if you like. Note that some things will look different depending on the theme you use, and the writing-style.css snippet might have to be modified. In my own vault I've tested it with the [Minimal](https://github.com/kepano/obsidian-minimal) theme.

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

- Writing Project Template - Creates the custom kanban views for new writing projects
- Writing Template - This is the important one, and the most complex. This and the following templates are used internally by the kanban board and are not intended to be used separately This is called from any note you create from the kanban project page, and it applies different templates depending on which list the note is generated from. It moves them to matching sub folders and fills out some of the properties.
- New Draft Template - This gets inserted into the project kanban to create a new draft list.
- Scene Template - Notes created from a draft kanban list will have this template applied. The story title, draft number, and a link to the project file will be automatically added in the properties. It will make a guess at the chapter number, which can be edited if you want to track that for your own use. It includes the writing css class that I describe below. It has a property used by a plugin I made that will update with the word count when focus switched away from the note.
- Character Template - Notes created from the Character kanban list will have this template applied. I've added some properties that I often use to help me flesh out a character, but those can be customized to suit the author.
- Writing Planning Template - Optional. This is just there because I wanted my planning notes to link back to the project page.

# Snippets

### writing_style.css

I spend a lot of time staring at a writing page, so I want it to be beautiful and functional. This snippet has been a work in progress for years, though I will say that I'm no expert on css, so feel free to let me know if there's a better way to do some of this. 

It makes the writing area an attractive dark on light (not harsh black on white) page that draws your attention to it and helps to differentiate the writing pages from other note pages. It loosely approximates the printed page by limiting line width and allowing for single line paragraph separation with indentation. It embeds the [IaWriter Duo font](https://ia.net/topics/in-search-of-the-perfect-writing-font) which is the best writing font out there. Horizontal rules become centered three-dot separators. Internal links blend into the rest of the text until hovered over. 
### hide_properties.css

Optional, but I think it's nice to hide the properties on scene pages so you can focus on the text you're writing. Hover over the property title to see and edit them, or open the Properties tab. 

### hide_dataview_error.css

This just hides the dataview error boxes on the project page.
