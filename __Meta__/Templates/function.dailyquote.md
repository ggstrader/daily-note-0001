<%*
quote = ''
await fetch('https://api.quotable.io/random')
    .then(response => response.json())
    .then(json => {
            quote = json.content;
            author = json.author;
            quote = '> ' + quote + '\n> —  ' + author;
        })
    .catch(err => console.log('Get Quote -> Failed', err));
quote = `>[!quote]\n${quote}`.replace(/(.*>)/s,"$1\n");
return quote
%>