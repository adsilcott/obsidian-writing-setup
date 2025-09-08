<%* 
const draft = await tp.system.prompt("Draft Number"); 
const folder = tp.file.folder(true) + "/📝 Draft " + draft;
const path = folder + "/";
-%>

## 📝 Draft <% draft %><br>```dataview<br>TABLE WITHOUT ID "Word Count: " + sum(rows.word_count) AS ""<br>FROM "<% folder %>"<br>WHERE word_count<br>GROUP BY true<br>```
- [ ] Draft <% draft %> inline notes:
    ```dataview
	LIST note
	FROM "<% folder %>"
	WHERE note
	```



