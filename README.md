# Grid Template Area Build & Burn

## Steps
1. `mkdir gridAreaBB && cd gridAreaBB`
2. `touch main.css index.html README.md`
3. `lite-server`
4. `code .`
5. Create HTML5 boiler-plate
6. Connect style to header if it isn't already: `<link rel="stylesheet" type="text/css" media="screen" href="main.css"/>`
7. Paste this inside `<body>` tag
* `div.wrapper>header.b+(nav.b>ul>li*4)+main.b+section.section1.b+section.section2.b+aside.b+footer.b`
NOTE: After pasting, you might need to delete the last letter `b`, then re-type `b` so the line highlights and can be selected
8. Add placeholder content inside the elements. Type the following in the specified tags
* `lorem5` in `header`
* `lorem1` in each of the 4 `li` tags
* `lorem100` in `main`
* `lorem50` in both `section` tags
* `lorem25` in `aside`
* `lorem20` in `footer`
9. Paste this in main.css file:
* `.b {
    border: 1px solid black;
    border-radius: 5px;
    background-color: lightcyan;
    padding: .5em;
}`


