<%*
let regex = /.*\/Wallpapers.*(?:\.jpg|\.jpeg|\.png)/;

function randomNumber(min, max)  { return Math.random() * (max - min) + min; }
function getFiles(used) {
    return app.vault.getFiles().filter(f =>
        f.path.match(regex)
    ).filter(f => !used.has(f.name))
}

let used = tp.file.find_tfile("utility.usedWallpapers");
let usedWps = new Set((await this.app.vault.read(used)).split("\n"));
let files = getFiles(usedWps);

if (files?.length === 0) {
  this.app.vault.modify(used, "");
  files = getFiles(new Set());
}
let rand = Math.floor(randomNumber(0, files.length));
let wp = files[rand];
tR += wp.path
this.app.vault.append(used, wp.name + '\n');
%>