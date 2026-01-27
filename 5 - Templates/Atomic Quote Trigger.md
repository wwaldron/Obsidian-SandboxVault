<%*

// Get the Name of the Person being Quoted
let name, work, description
name = await tp.system.prompt("What is the name of the person being quoted?", "", true, false)

// Get the Name of the Work Being Quoted
work = await tp.system.prompt("What is the title of the work being quoted?", "", true, false)

// Give a short description about the quote
description = await tp.system.prompt("Give a one or two word description of the quote.", "", true, false)

// Set the Final Name
let final_name
final_name = name + " - " + work + " - " + description + " Quote"
tR += "!\[\[" + final_name + "#^111111\]\]"
tp.file.create_new(tp.file.find_tfile("Atomic Quote Template"), final_name, true, app.vault.getAbstractFileByPath("1 - Atlas/Quotes"))

%>
