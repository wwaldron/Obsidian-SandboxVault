<%*

// Because of these Lines, this has to be run from a Course Note
let fPath = tp.file.folder(true);
fPath += "/" + tp.file.title + " - Chapters";
console.log(fPath)

// Get Number of Existing Chapter Files
var j = 1;
const files = app.vault.getMarkdownFiles();
files.forEach((file) => {
	if (file.path.includes(fPath) && file.basename.includes("Chapter")) {
		j += 1;
	};
})

// Get New File Name
const r = ('0' + j.toString()).slice(-2);
const fName = tp.file.title + " - Chapter " + r;

tp.file.create_new(tp.file.find_tfile("Chapter Note Template"), fName, true, fPath)
%>
