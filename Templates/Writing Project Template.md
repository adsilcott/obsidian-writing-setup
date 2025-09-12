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
  - hide-dataview-error
kanban-plugin: list
---

## Project `INPUT[text:writing_project_title]` Status:`INPUT[text:status]` `BUTTON[add-draft,add-draft-from-compilation]`<br>```meta-bind-button<br>label: Add Draft<br>style: primary<br>id: add-draft<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: contentStart<br>    value: "Templates/New Draft Template"<br>    templater: true<br>```<br>```meta-bind-button<br>label: From Compilation<br>icon: ""<br>style: primary<br>class: ""<br>cssStyle: ""<br>backgroundImage: ""<br>tooltip: ""<br>id: add-draft-from-compilation<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: 0<br>    value: Some text<br>    templater: false<br>```



## 💡Planning



## 👫 Characters



## ☑️ Notes



## 📚 Compilations





%% kanban:settings
```
{"kanban-plugin":"list","list-collapse":[],"lane-width":260,"full-list-lane-width":true,"new-note-template":"Templates/Writing Template.md","metadata-keys":[{"metadataKey":"card_notes","label":"Notes","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"synopsis","label":"Synopsis","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"summary","label":"Summary","shouldHideLabel":true,"containsMarkdown":false}],"show-checkboxes":false}
```
%%