<%* 
const draft = await tp.system.prompt("Draft Number"); 
const folder = tp.file.folder(true) + "/📝 Draft " + draft;
//const path = folder + "/";
const items = tp.app.vault.getMarkdownFiles().filter(x => x.path.startsWith(tp.file.folder(true)));
const selectedItem = (await tp.system.suggester((item) => item.basename, items));
const selectedContent = await app.vault.cachedRead(selectedItem);
var chapters = selectedContent.split("# ");
chapters.shift();
//Add list
tR += '## 📝 Draft ' + draft + '<br>```dataview<br>LIST sum(rows.word_count)<br>FROM "' + folder + '"<br>WHERE word_count<br>GROUP BY "Word Count"<br>```<br>Inline Notes:<br>```dataview<br>LIST note<br>FROM "' + folder + '"<br>WHERE note<br>```\n\n\n';
//Add chapters
chapters.forEach (async (ch) => {
	var label = ch.split('\n')[0];
	await var file = tp.file.create_new(ch, label, false, folder);
	//var link = tp.app.filemanager.generateMarkdownLink(file, folder)
	tR += '- [' + label + ']\n';
});
tR += "\n\n";
-%>
