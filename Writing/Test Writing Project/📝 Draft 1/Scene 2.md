---
type: scene
up: "[[Test Writing Project - Project]]"
story: Test Writing Project
draft: 1
chapter: 2
synopsis:
characters:
spellcheck: false
word_count: 205
cssclasses:
  - writing
  - hidden-properties
  - scene-break
---
# Headings and Sections
A first level heading on the first line can be used to add a title to a chapter. If it's missing then the file name is used when the draft is compiled.

---

It's common to split chapters into sections. You can use three dashes: "---" to create a visual divider between sections. In markdown these are normally turned into horizontal lines, but here they become three dot section breaks, similar to what you might see in a book. Always put an empty line before them -- it's a markdown quirk.

## This is a labeled section
This is an even better way to organize sections. 2nd level headings will be turned to scene breaks. Since sections aren't typically labeled, the header text hidden is until edited, or if the section is folded by clicking on the arrow. 

## This is a section too
This way you can use the outline side panel on the right to help you visualize the chapter flow and even drag and drop to rearrange sections. Try it! They will be replaced with a scene break in compilation. If you don't like this behavior remove the "scene-break" value from the "cssclasses" property in the scene template.

