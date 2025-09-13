<%* 
const draft = await tp.system.prompt("Draft Number"); 
const inFolder = tp.file.folder(true) + "/Import";
const fileList = app.vault.getMarkdownFiles().filter(x => x.path.startsWith(inFolder));
const inFile = (await tp.system.suggester((item) => item.basename, fileList)).basename;
const newFolder = tp.file.folder(true) + "/📝 Draft " + draft;
const path = newFolder + "/";

-%>

## 📝 Draft <% draft %><br>```dataview<br>LIST sum(rows.word_count)<br>FROM "<% newFolder %>"<br>WHERE word_count<br>GROUP BY "Word Count"<br>```<br>Inline Notes:<br>```dataview<br>LIST note<br>FROM "<% newFolder %>"<br>WHERE note<br>```



