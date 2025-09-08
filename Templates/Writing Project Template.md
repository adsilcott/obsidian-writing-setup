<%* 
const projectName = await tp.system.prompt("Project Name");
await tp.file.move("Writing/" + projectName + "/" + projectName + " - Project");
-%>
---
up: "[[Writing Projects Homepage]]"
writing_project_title: <% projectName %>
priority:
status:
cssclasses:
  - writing-project
kanban-plugin: list
---

## Project

- [ ] `INPUT[text:writing_project_title]` Project Title
- [ ] `INPUT[text:status]` Status
- [ ] ```meta-bind-button
	style: plain
	label: Add Draft
	action:
	 type: insertIntoNote
	 line: 10
	 value: "Templates/New Draft Template"
	 templater: true
	```



## 💡Planning



## 👫 Characters



## ☑️ Notes



## 📚 Compilations





%% kanban:settings
```
{"kanban-plugin":"list","list-collapse":[],"lane-width":260,"full-list-lane-width":true,"new-note-template":"Templates/Writing Template.md","metadata-keys":[{"metadataKey":"card_notes","label":"Notes","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"synopsis","label":"Synopsis","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"summary","label":"Summary","shouldHideLabel":true,"containsMarkdown":false}],"show-checkboxes":false}
```
%%