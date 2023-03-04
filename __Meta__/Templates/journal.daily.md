---
tags: 
- "life/journal"
- "d/<% tp.date.now('YYYY/MM/DD', 0, tp.file.title, 'YYYY.MM.DD') %>"
aliases: 
- "<% tp.date.now("MMMM Do, YYYY", 0, tp.file.title, "YYYY.MM.DD") %>"
banner: "<%await tp.file.include('[[function.randomWallpaper]]')%>"
cssClass: daily
banner_y: 0
---
`class:cc-large-title-secondary`
# ⚜ <% tp.date.now("dddd DD",0,tp.file.title, "YYYY.MM.DD") %> ⚜
`class:cc-large-title`
# <% tp.date.now("MMMM YYYY",0,tp.file.title, "YYYY.MM.DD") %>

`class:cc-daily-collection`
- [[<% tp.date.now("YYYY",0,tp.file.title, "YYYY.MM.DD") %>|Day <% moment(tp.file.title,'YYYY.MM.DD').dayOfYear() %>]] <div class="bar"><progress value="<% moment(tp.file.title,'YYYY.MM.DD').dayOfYear() %>" max="365" text=“text” data-label="🝮 <% moment(moment(tp.file.title,'YYYY.MM.DD').endOf('year')).diff(moment(tp.file.title,'YYYY.MM.DD'),'days') %> days remain"/></div> `class:cc-daily-progress`
- [[<% tp.date.now(' YYYY-[Q]Q',0,tp.file.title, 'YYYY.MM.DD') %>|<% tp.date.now("Qo",0,tp.file.title, "YYYY.MM.DD") %> Quarter]] <div class="bar"><progress value="<% moment(moment(tp.file.title,'YYYY.MM.DD')).diff(moment(tp.file.title,'YYYY.MM.DD').startOf('quarter'),'days') %>" max="<% moment(moment(tp.file.title,'YYYY.MM.DD').endOf('quarter')).diff(moment(tp.file.title,'YYYY.MM.DD').startOf('quarter'),'days') %>" data-label="🝮 <% moment(moment(tp.file.title,'YYYY.MM.DD').endOf('quarter')).diff(moment(tp.file.title,'YYYY.MM.DD'),'days') %> days remain"/></div> `class:cc-daily-progress`
- [[<% tp.date.now(" gggg-[W]ww",0,tp.file.title,"YYYY.MM.DD") %>|Week <% tp.date.now("ww",0,tp.file.title, "YYYY.MM.DD") %>]] <div class="bar"><progress value="<% tp.date.now('DD',0,tp.file.title, 'YYYY.MM.DD') %>" max="<% moment(tp.file.title,'YYYY.MM.DD').daysInMonth() %>" text=“text” data-label="🝮 <% moment(moment(tp.file.title,'YYYY.MM.DD').endOf('month')).diff(moment(tp.file.title,'YYYY.MM.DD'),'days') %> days left in <% tp.date.now('MMMM',0,tp.file.title, 'YYYY.MM.DD') %>"/></div> `class:cc-daily-progress`
`````col
````col-md
flexGrow=1
===
<%await tp.file.include("[[function.randomSong]]")%>  
````
````col-md
flexGrow=1
===
<%await tp.file.include("[[function.dailyquote]]")%>
````
`````

`class:cc-prominent-text,cc-center`
# Todays Goals
`class:cc-inset`
<%*
let which = [];
if (tp.date.now("M-D",0, tp.file.title) == "1-1") {
  which = ['Yearly',...which]
} 
if (tp.date.now("D",0, tp.file.title) == 1) {
	which = ['Monthly',...which];
}
if (tp.date.now("ddd", 0, tp.file.title) == "Sun") { 
	which = ['Weekly',...which];
} 	
console.log(which)
tR += which.map(w => `- [ ] Make ${w} Note\n`).join('\n');
%><%await tp.file.include("[[function.randomGoals]]")%>	

`class:cc-center,cc-prominent-text`
### Daily Quote
`class:cc-inset` 
Reflect on the daily quote...

`class:cc-center,cc-prominent-text`
### Anything
`class:cc-inset` 
Write what's on your mind...

