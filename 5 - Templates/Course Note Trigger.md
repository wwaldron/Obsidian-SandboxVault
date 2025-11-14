<%*

let code, name, startDate, endDate
code = await tp.system.prompt("What is the course code (e.g., PHYS 2230)?", "", true)
name = await tp.system.prompt("What is the course name (e.g., Classical Mechanics)?", "", true)
// startDate = await tp.system.prompt("What is the course start date (e.g. 2025-01-25)", "", true)
// startDate = await tp.system.prompt("What is the course end date (e.g. 2025-12-31)", "", true)

tp.file.create_new(tp.file.find_tfile("Course Note Template"), code + " - " + name, true)

%>