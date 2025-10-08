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
let thisFile = tp.config.target_file;
let thisFileLink = tp.app.fileManager.generateMarkdownLink(thisFile, thisFile.path);
let position = 1;
for (const ch of chapters)
{
	let label = ch.split('\n')[0];
	let file = await tp.file.create_new(await tp.file.find_tfile("Scene Template"), label, false, folder);
	let content = ch.replace(label, '').replace(/\n\s*\n/g, '\n').replace(/---/g, '\n---\n').trim();
	//content = content;
	await app.vault.adapter.append(file.path, content);
	
	await app.fileManager.processFrontMatter(file, frontmatter => {
		if ('up' in frontmatter) frontmatter['up'] = thisFileLink;
		if ('story' in frontmatter) frontmatter['story'] = tp.frontmatter["story"];
		if ('draft' in frontmatter) frontmatter['draft'] = draft;
		if ('chapter' in frontmatter) frontmatter['chapter'] = position++;
	});

	let link = await tp.app.fileManager.generateMarkdownLink(file, file.path, "", label);
	tR += '- ' + link + '\n';
}
tR += "\n\n";
-%>
