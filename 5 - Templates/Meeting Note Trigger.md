<%*

let type, name, topic, held
held = tp.date.now("YYYY-MM-DD")
topic = "o "
type = await tp.system.suggester(["with a specific person", "meeting with a custom name", "no specific people nor names"], ["with a specific person", "meeting with a custom name", "no specific people nor names"], false, "What kind of meeting it was?")

if (type == "with a specific person") name = await tp.system.prompt("What was their first and second name?", "Meeting with ", true, false)
else if (type == "meeting with a custom name") name = await tp.system.prompt("What was the meeting called then?", "", true, false)
else if (type == null || type == "no specific people nor names") name = "" 

topic = await tp.system.prompt("What was the meeting about?", "about ", true, false)
if (topic == "about ") topic = ""

let final_name = name
if (name.length > 0 && topic.length > 0) final_name += " "

let triggered_date = tp.date.now("YYYY-MM-DD", 0, tp.file.title, "DDDD - dddd, MMMM D, YYYY")
if (held != triggered_date) {
	if (await tp.system.prompt("You triggered this meeting in a note from " + triggered_date + ". Do you want to use this date instead of today's? y / ESC", false, false, false) == "y") held = triggered_date
}

final_name += topic + " - " + held

tR += name + " - **Quick Summary**\n"
tR += "!\[\[" + final_name + "#^3d1233\]\]"
tp.file.create_new(tp.file.find_tfile("Meeting Note Template"), final_name, true, app.vault.getAbstractFileByPath("2 - Calendar/Meetings"))

%>