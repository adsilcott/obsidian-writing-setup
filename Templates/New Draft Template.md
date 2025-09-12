<%* 
const draft = await tp.system.prompt("Draft Number"); 
const folder = tp.file.folder(true) + "/📝 Draft " + draft;
const path = folder + "/";
-%>

## 📝 Draft <% draft %><br>```dataview<br>LIST sum(rows.word_count)<br>FROM "<% folder %>"<br>WHERE word_count<br>GROUP BY "Word Count"<br>```<br>Inline Notes:<br>```dataview<br>LIST note<br>FROM "<% folder %>"<br>WHERE note<br>```



