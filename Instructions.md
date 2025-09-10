#### Homepage
Open "Writing Projects Homepage". You can check out the test project or use the "Create New Project" button to create a new one. The example "Test Writing Project" folder can be deleted once you're ready. 

Here you can see all writing projects created in this system. In the table you can rename them and set a status, and in the far left column you can enter a number. Higher numbers sort to the top, which can help you organize the list. If preferred you could sort my date modified, but note that only counts changes to the project page.

#### Project Page
Each project page is a kanban board (in vertical list mode so it can be placed in a sidebar) with several lists already created. You can add more lists and rearrange them however you like. For example you could add a Timeline list and add links to scenes and characters to help you plan your story flow. Note that you can collapse any lists/drafts you don't want to see to keep things organized. 

All files for the project should be created from this page so the proper templates and properties can be added to them. This is done by adding cards, then using the "New note from card" option. More on this below.

You can drag the tab this page is in to the sidebar if you like -- if you do it's a good idea to pin it with the tab context menu so any files you open from it open in a separate tab.

The Project list contains some important cards. The Project Title and Status can be changed here, but you have to double click on the text, then click into the text box, make the change, then click the label and hit enter. This is a limitation of the plugins being used, so it's usually easier to switch back to the Writing Projects Homepage to make those changes. 

#### New Draft
To start a new draft click "Add Draft" under the Project list. After you enter a number a new draft list will be created at the top of the page. The first card on the list is a special note item that can be moved to the "Notes" list, it simply displays any notes you've added to that draft in the form of: 
```
[note::Add note text here] 
```

At the top of the Draft list is a Dataview box which is empty, but will display the word count for the draft once you start.

Once you have some scenes created you can use this list to find scenes and rearrange the order.

#### New Scene
To create a scene, click "+ Add a card" in the Draft list. Name it what you want the chapter or scene to be called, then click on the three dot dropdown for that item and choose, "New note from card". This will open a new tab to the right. You can move this tab wherever you like.

The scene view is intended to look more like a printed page than markdown, with dark on light text by default. These colors can be edited in the "writing_style.css" snippet. Note that you can separate paragraphs with one return and each will be indented. If you collapse both side bars then it's a pretty clean writing area.

Properties are hidden but can be accessed by hovering over the Properties title at the top of the page, or by opening the Properties sidebar. Story title and draft should be filled in automatically, and the template will guess at the chapter number, but you can change that to any number. If you fill in the "synopsis" property, that information will show up in the draft scene list. Wordcount will be updated automatically when you click away from the scene tab. Spellchecking is disabled by default but can be toggled on by the property. The plugin that does this is a little finicky, so you might have to start typing for it to take effect.

#### Characters
The idea of the Character list is to be a handy reference while you're writing. If you keep the project page open to the side you can hover over a character link to see a preview of the character note (or any other note). This is great to quickly remember a detail about a character as you're writing without switching away from what you're doing.

To create a character note hit "+ Add a card" in the Character list and enter the character name. I usually use the common name for reasons I'll explain later. Once again, open the three dot context menu and select "New note from card". This will create a character note with fields you can fill in. If you fill in the "At a glance" summary field, that will show up on the character list in the project file. Any additional character information can be added after the fields or wherever, and the default fields can be changes in the Character Template file. 

A little trick: If you're unsure of a character name, you can create a note with a temporary name, and wherever you mention them in the story use a link to that file, for example: This is what [Bob] did. The link brackets will be hidden in the scene view unless you hover over it, and if you change the name of the character file it will change the name everywhere you've linked to it. When you compile the story the links will be removed. From the scene view you can also hold Ctrl while mousing over the link to see character details.

#### Planning
The planning list is intended to contain any notes you make for your project, including outlines, research, random thoughts and ideas, or anything else. You can turn any of these into a note by using the usual "New note from card" option. This will apply a custom template with some properties auto filled. The template for planning notes can be changed in "Writing Planning Template".

#### Compilation
To compile several chapters into one file for export, create a new card in the Compilations list and do "New note from card". It will ask for a draft number, then it will combine all of the scene files in that draft list into one file. It ignores the "chapter" property numbers and instead uses the list order, so make sure your scenes are listed in the order you want them before you do this. 

Since the writing_style snippet encourages you to use single returns to separate paragraphs, those will show up incorrectly with most other styles. An important thing this compiler does is to add the extra lines back in between paragraphs so they read as separate. It also removes the frontmatter. 

The resulting file will be ready to export to a docx or pdf using the Enhancing Export plugin (once Pandoc is installed).
