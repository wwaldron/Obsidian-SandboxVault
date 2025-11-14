<%*

let type, name, topic, received
received = tp.date.now("YYYY-MM-DD")
topic = "o "
type = await tp.system.suggester(["from a specific person", "email with a custom name"], ["from a specific person", "email with a custom name"], false, "What kind of email it was?")

if (type == "from a specific person") name = await tp.system.prompt("What was their first and second name?", "Email from ", true, false)
else if (type == "email with a custom name") name = await tp.system.prompt("What was the email about then?", "", true, false)

topic = await tp.system.prompt("What was the email about?", "about ", true, false)
if (topic == "about ") topic = ""

let final_name = name
if (name.length > 0 && topic.length > 0) final_name += " "

let triggered_date = tp.date.now("YYYY-MM-DD", 0, tp.file.title, "DDDD - dddd, MMMM D, YYYY")
if (received != triggered_date) {
	if (await tp.system.prompt("You triggered this email note in a note from " + triggered_date + ". Do you want to use this date instead of today's? y / ESC", false, false, false) == "y") received = triggered_date
}

final_name += topic + " - " + received

tR += name + " - **Quick Summary**\n"
tR += "!\[\[" + final_name + "#^e421fe\]\]"
tp.file.create_new(tp.file.find_tfile("Email Template"), final_name, true, app.vault.getAbstractFileByPath("2 - Calendar/Emails"))

%>