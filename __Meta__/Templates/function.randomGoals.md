<%*  
// this regex splits the file by headings into groups without the headings  
let regex = /#.*\n((?:.+\n)+)/gm;  
let goals = tp.file.find_tfile("utility.Goals");  
let contents = await this.app.vault.read(goals);  
let matches = contents.replace(regex, "$1").split("\n\n");

// for each group, select a random line and add it to the string 'tR'  
for (const g of matches) {  
	// split the group into lines (non-empty)  
	let lines = g.split("\n").filter((l) => l.length > 0);  
	tR += `- [ ] ${lines[Math.floor(Math.random() * lines.length)]}\n` ;  
}  
tR = tR.trim()  
%>