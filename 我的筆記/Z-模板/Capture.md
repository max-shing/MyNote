<%*
const file = tp.file.find_tfile(tp.date.now("YYYY-MM-DD_ddd"))
if (file) {
	const loggedItem = await tp.system.prompt("什麼事?")
	const time = tp.date.now("HH:mm")
	const content = (await app.vault.read(file)).split("\n")
	const index = content.indexOf("### What happened today?")
	content.splice(index + 1, 0, `- ${time} - ${loggedItem}`)
	await app.vault.modify(file, content.join("\n"))
} else {
new Notification("No Daily Note Found!")
}
-%>