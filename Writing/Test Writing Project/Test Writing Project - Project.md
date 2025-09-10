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


## Project

- [ ] `INPUT[text:writing_project_title]` Project Title
- [ ] `INPUT[text:status]` Status
- [ ] `BUTTON[add-draft,add-draft-from-compilation]`
	```meta-bind-button
	label: Add Draft
	icon: ""
	style: primary
	class: ""
	cssStyle: ""
	backgroundImage: ""
	tooltip: ""
	id: add-draft
	hidden: true
	actions:
	  - type: insertIntoNote
	    line: 0
	    value: Some text
	    templater: false
	```
	```meta-bind-button
	label: Add Draft From Compilation
	icon: ""
	style: primary
	class: ""
	cssStyle: ""
	backgroundImage: ""
	tooltip: ""
	id: add-draft-from-compilation
	hidden: true
	actions:
	  - type: insertIntoNote
	    line: 0
	    value: Some text
	    templater: false
	```


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