---

up: "[[Writing Projects Homepage]]"
writing_project_title: Test Writing Project
priority:
status: in progress
cssclasses:
  - hide-dataview-error
kanban-plugin: list

---

## 📝 Draft 1<br>```dataview<br>TABLE WITHOUT ID "Word Count: " + sum(rows.word_count) AS ""<br>FROM "Writing/Test Writing Project/📝 Draft 1"<br>WHERE word_count<br>GROUP BY true<br>```

- [ ] [[Scene 1]]


<<<<<<< Updated upstream
<<<<<<< Updated upstream
## Project `INPUT[text:writing_project_title]` Status:`INPUT[text:status]` `BUTTON[add-draft,add-draft-from-compilation]`<br>```meta-bind-button<br>label: Add Draft<br>icon: ""<br>style: primary<br>class: ""<br>cssStyle: ""<br>backgroundImage: ""<br>tooltip: ""<br>id: add-draft<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: 0<br>    value: Some text<br>    templater: false<br>```<br>```meta-bind-button<br>label: From Compilation<br>icon: ""<br>style: primary<br>class: ""<br>cssStyle: ""<br>backgroundImage: ""<br>tooltip: ""<br>id: add-draft-from-compilation<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: 0<br>    value: Some text<br>    templater: false<br>```
=======
## Project `INPUT[text:writing_project_title]` Status:`INPUT[text:status]` `BUTTON[add-draft,add-draft-from-compilation]`<br>```meta-bind-button<br>label: Add Draft<br>style: primary<br>id: add-draft<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: contentStart<br>    value: "Templates/New Draft Template"<br>    templater: true<br>```<br>```meta-bind-button<br>label: From Compilation<br>icon: ""<br>style: primary<br>class: ""<br>cssStyle: ""<br>backgroundImage: ""<br>tooltip: ""<br>id: add-draft-from-compilation<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: contentStart<br>    value: "Templates/New Draft From Compilation Template"<br>    templater: true<br>```
>>>>>>> Stashed changes
=======
## Project `INPUT[text:writing_project_title]` Status:`INPUT[text:status]` `BUTTON[add-draft,add-draft-from-compilation]`<br>```meta-bind-button<br>label: Add Draft<br>style: primary<br>id: add-draft<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: contentStart<br>    value: "Templates/New Draft Template"<br>    templater: true<br>```<br>```meta-bind-button<br>label: Decompile<br>icon: ""<br>style: primary<br>class: ""<br>cssStyle: ""<br>backgroundImage: ""<br>tooltip: ""<br>id: add-draft-from-compilation<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: contentStart<br>    value: "Templates/Decompile Template"<br>    templater: true<br>```
>>>>>>> Stashed changes



## 💡Planning



## 👫 Characters

- [ ] [[Bob]]


## ☑️ Notes

- [ ] Draft 1 inline notes:
	```dataview
	LIST note
	FROM "Writing/Test Writing Project/📝 Draft 1"
	WHERE note
	```


## 📚 Compilations



## Import





%% kanban:settings
```
{"kanban-plugin":"list","list-collapse":[false],"lane-width":260,"full-list-lane-width":true,"new-note-template":"Templates/Writing Template.md","metadata-keys":[{"metadataKey":"card_notes","label":"Notes","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"synopsis","label":"Synopsis","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"summary","label":"Summary","shouldHideLabel":true,"containsMarkdown":false}],"show-checkboxes":false}
```
%%