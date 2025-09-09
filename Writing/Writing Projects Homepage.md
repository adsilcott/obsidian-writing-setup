
```meta-bind-button
style: primary
label: Create New Project
id: new-project
hidden: true
actions:
  - type: templaterCreateNote
    templateFile: "Templates/Writing Project Template.md"
    folderPath: Writing
    fileName: "Temp Project Name"
```
# Projects  `BUTTON[new-project]`

---
```base
views:
  - type: table
    name: Table
    filters:
      and:
        - file.hasProperty("writing_project_title")
    order:
      - priority
      - file.name
      - writing_project_title
      - status
    sort:
      - property: priority
        direction: DESC
      - property: file.mtime
        direction: DESC
      - property: writing_project_title
        direction: ASC
    columnSize:
      note.priority: 41
      file.name: 164
      note.writing_project_title: 256
      note.status: 105

```
