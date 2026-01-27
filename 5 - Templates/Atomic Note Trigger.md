<%*

// Get metadata from the calling file
const currentFile = tp.file.find_tfile(tp.file.title);
let authorOrPerson = "";

if (currentFile) {
  const fm = app.metadataCache.getFileCache(currentFile)?.frontmatter;

  if (fm) {
    // Check for various author/person fields in order of priority
    if (fm.authors !== undefined) {
      // Handle array or single value for authors
      const authorsArray = Array.isArray(fm.authors) ? fm.authors : [fm.authors];
      authorOrPerson = authorsArray[0] || "";
      // Remove wiki link brackets if present
      authorOrPerson = authorOrPerson.replace(/\[\[|\]\]/g, "");
    } else if (fm.hosts !== undefined) {
      const hostsArray = Array.isArray(fm.hosts) ? fm.hosts : [fm.hosts];
      authorOrPerson = hostsArray[0] || "";
      authorOrPerson = authorOrPerson.replace(/\[\[|\]\]/g, "");
    } else if (fm.instructor !== undefined) {
      const instructorArray = Array.isArray(fm.instructor) ? fm.instructor : [fm.instructor];
      authorOrPerson = instructorArray[0] || "";
      authorOrPerson = authorOrPerson.replace(/\[\[|\]\]/g, "");
    } else if (fm.speaker !== undefined) {
      authorOrPerson = fm.speaker;
      authorOrPerson = authorOrPerson.replace(/\[\[|\]\]/g, "");
    }
  }
}

// If no author/person found in metadata, prompt the user
if (!authorOrPerson || authorOrPerson.trim() === "") {
  authorOrPerson = await tp.system.prompt("Who is the author/person associated with this note?", "", true, false);
}

// Get the title from the calling file's frontmatter
let title = "";
if (currentFile) {
  const fm = app.metadataCache.getFileCache(currentFile)?.frontmatter;
  if (fm && fm.title) {
    title = fm.title;
  } else {
    title = tp.file.title;
  }
} else {
  title = tp.file.title;
}

// Sanitize title for use in filename (remove invalid characters)
title = title.replace(/[\\/:*?"<>|]/g, "");

// Get a description of what the atomic note is about
let about = await tp.system.prompt("What is this atomic note about? (short description)", "", true, false);

// Construct the final file name
let finalName = authorOrPerson + " - " + title + " - " + about;

// Store the calling file name for the parent link
let callingFileName = tp.file.title;

// Create the new atomic note file in 0 - Incoming
const newFile = await tp.file.create_new(
  tp.file.find_tfile("Atomic Note Template"),
  finalName,
  false,
  app.vault.getAbstractFileByPath("0 - Incoming")
);

// Add the parent link to the newly created file
if (newFile) {
  await tp.file.move(`0 - Incoming/${finalName}`, newFile);

  // Read the newly created file and update the parent property
  let content = await app.vault.read(newFile);
  content = content.replace(/^parent:.*$/m, `parent: "[[${callingFileName}]]"`);
  await app.vault.modify(newFile, content);

  // Open the newly created file
  await app.workspace.getLeaf().openFile(newFile);
}

%>
