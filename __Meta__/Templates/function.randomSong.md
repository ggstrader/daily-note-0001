<%*
let regex = /.*\/Song Library.*(?:\.webm|\.mp3|\.mp4|\.m4a|\.aac)/;

function randomNumber(min, max)  { return Math.random() * (max - min) + min; }
function getFiles(used) {
    return app.vault.getFiles().filter(f =>
        f.path.match(regex)
    ).filter(f => !used.has(f.name))
}

let used = tp.file.find_tfile("utility.usedSongs");
let usedSongs = new Set((await this.app.vault.read(used)).split("\n"));
let files = getFiles(usedSongs);

if (files?.length === 0) {
  this.app.vault.modify(used, "");
  files = getFiles(new Set());
}
let rand = Math.floor(randomNumber(0, files.length));
let song = files[rand];
tR += `\`\`\`audio-player\n[[${song.name}]]\n\`\`\`\n`;
this.app.vault.append(used, song.name + '\n');

%>