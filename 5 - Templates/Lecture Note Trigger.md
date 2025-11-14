<%*

// Because of these Lines, this has to be run from a Course Note
let fPath = tp.file.folder(true);
fPath += "/Lectures";
//console.log(fPath)

// Get Number of Existing Lecture Files
var j = 1;
const files = app.vault.getMarkdownFiles();
files.forEach((file) => {
	if (file.path.includes(fPath)) {
		j += 1;
	};
})

// Get New File Name
const r = ('0' + j.toString()).slice(-2);
const fName = tp.file.title + " - Lecture " + r;
//console.log(fName)

tp.file.create_new(tp.file.find_tfile("Lecture Note Template"), fName, true, fPath)
//console.log('Made It')
%>
