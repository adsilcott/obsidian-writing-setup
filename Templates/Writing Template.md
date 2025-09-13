
<%*
// Get the kanban file this was created from
const lastFiles = app.workspace.getLastOpenFiles();
// Because Kanban always opens a new pane, it's always the last file
const parentFile = tp.file.find_tfile(lastFiles[0]);
const parentLink = app.fileManager.generateMarkdownLink(parentFile, tp.file.folder(true));
// Get parent note content
const cont = await app.vault.cachedRead(parentFile);
let title = "No Title Defined";
await app.fileManager.processFrontMatter(parentFile, (frontmatter) =>{
	title = frontmatter['writing_project_title'];
});
// Look at each kanban list and find the one that links to this file
const lists = cont.split("## ");
lists.splice(0,1);
// When template is run, file is not yet linked, so get list that
// has same name item but avoid any previous links to same-named files.
const i = lists.findIndex((e) => e.includes(tp.file.title) && !e.includes(tp.file.title + "]]"));
let folder = "Default";
let position = 0;
if (i > -1) {
	// This should give list name
	folder = lists[i].split(/\n|<br>/)[0]; 
	let s2 = lists[i].split("- ");
	position = s2.findIndex((e) => e.includes(tp.file.title));
	if (lists[i].includes("inline notes")) position -= 1;
}
//Move note to matching folder
let path = parentFile.path;
path = path.substring(0, path.lastIndexOf('/'));
await tp.file.move(path + "/" + folder + "/" + tp.file.title);
// Apply templates based on list

// DRAFT
if (folder.includes("Draft")) {
	const draft = parseFloat(folder.replace("📝 Draft", ""));
	tR = await tp.file.include("[[Scene Template]]");
	tp.hooks.on_all_templates_executed(async () => {
		await app.fileManager.processFrontMatter(tp.config.target_file, frontmatter => {
			frontmatter['up'] = parentLink
		    frontmatter['story'] = title
			frontmatter['draft'] = draft
			frontmatter['chapter'] = position //This is a guess based on position in list
		});
	});
}

// CHARACTER
else if (folder.includes("Character")) {
	tR = await tp.file.include("[[Character Template]]");
	tp.hooks.on_all_templates_executed(UpdateMeta);
}

// PLANNING
else if (folder.includes("Planning")) {
	tR = await tp.file.include("[[Writing Planning Template]]");
	tp.hooks.on_all_templates_executed(UpdateMeta);
}

// COMPILE
//Concatenate draft into one file in "Compiler" or "Compilations"
else if (folder.includes("Compil")) {
	let drafts = [];
	let draftList = [];
	//Get list of drafts and the contents of each
	lists.forEach((e) => {
		let l = e.substring(0,e.indexOf("\n"));
		l = l.substring(0,l.indexOf("<br>"));
		if (l.includes("Draft")) {
			drafts.push(l);
			draftList.push(e);
		}
	});
	//Let user select draft
	let compDraft = await tp.system.suggester(drafts, draftList);
	let compList = compDraft.split("\n");

	//Get path to avoid ambiguity
	let thisPath = tp.file.path(true);
	let draftPath = thisPath.substring(0, thisPath.lastIndexOf('/', thisPath.lastIndexOf('/')-1)) + "/" + compList[0].split("<br>")[0] + "/";
	//Check each line
	compList.forEach(async (e) => 
	{
		if (e.includes("- [ ] [["))
		{
			// Open each file and add to current
			const path = draftPath + e.substring(e.indexOf('[[')+2, e.indexOf(']]'));
			console.log(path);
			const chapterFile = tp.file.find_tfile(path);
			let chapter = await app.vault.cachedRead(chapterFile);
			//Add extra newline
			chapter = chapter.replace(/\n/g,"\n\n");
			//Remove internal links
			chapter = chapter.replace(/\[\[/g, "").replace(/\]\]/g, "");
			//Remove frontmatter
			tR += chapter.substring(chapter.indexOf('---', chapter.indexOf('---')+3)+3) + "\n\n---\n";
		}
	});
}

async function UpdateMeta(){
	await app.fileManager.processFrontMatter(tp.config.target_file, frontmatter => {
		frontmatter['up'] = parentLink
		frontmatter['story'] = title
	});
}

-%>
