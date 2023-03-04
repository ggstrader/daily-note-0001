[Sass](https://sass-lang.com/install) allows you to write cleaner css. 

The command:
`sass --update --no-stop-on-error --watch .obsidian/snippets/scss:.obsidian/snippets/ -c` 

Will compile every file in the `scss` directory into it's own `.css` file to enable in Appearance settings. The `scss_parts` directory is for scss files that you want to include in other files, which don't need to have their own snippet.