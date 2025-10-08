---

up: "[[Writing Projects Homepage]]"
writing_project_title: Test Writing Project
priority:
status: in progress
cssclasses:
  - hide-dataview-error
kanban-plugin: list

---

## 📝 Draft 1<br>```dataview<br>LIST sum(rows.word_count)<br>FROM "Writing/Test Writing Project/📝 Draft 1"<br>WHERE word_count<br>GROUP BY "Word Count"<br>```<br>Inline Notes:<br>```dataview<br>LIST note<br>FROM "Writing/Test Writing Project/📝 Draft 1"<br>WHERE note<br>```

- [ ] [[Scene 1]]
- [ ] [[Scene 2]]


## Project `INPUT[text:writing_project_title]` Status:`INPUT[text:status]` `BUTTON[add-draft,add-draft-from-compilation]`<br>```meta-bind-button<br>label: Add Draft<br>style: primary<br>id: add-draft<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: contentStart<br>    value: "Templates/New Draft Template"<br>    templater: true<br>```<br>```meta-bind-button<br>label: Decompile<br>icon: ""<br>style: primary<br>class: ""<br>cssStyle: ""<br>backgroundImage: ""<br>tooltip: ""<br>id: add-draft-from-compilation<br>hidden: true<br>actions:<br>  - type: insertIntoNote<br>    line: contentStart<br>    value: "Templates/Decompile Template"<br>    templater: true<br>```



## 💡Planning



## 👫 Characters

- [ ] [[Bob]]


## 📚 Compilations

- [ ] [[C1]]


## Import





%% kanban:settings
```
{"kanban-plugin":"list","list-collapse":[],"lane-width":260,"full-list-lane-width":true,"new-note-template":"Templates/Writing Template.md","metadata-keys":[{"metadataKey":"card_notes","label":"Notes","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"synopsis","label":"Synopsis","shouldHideLabel":true,"containsMarkdown":false},{"metadataKey":"summary","label":"Summary","shouldHideLabel":true,"containsMarkdown":false}],"show-checkboxes":false}
```
%%