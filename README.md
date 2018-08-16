# Grid Template Area Step by Step

## Steps
1. Fork and clone this repo
2. In your terminal, `cd` into the folder
3. `lite-server`
4. Open the folder in your code editor - `code .` 
5. Create HTML5 boiler-plate
6. Connect style to header if it isn't already: `<link rel="stylesheet" type="text/css" media="screen" href="main.css"/>`
7. Paste below inside `<body>` tag to create the elements for the HTML
* `div.wrapper>header.b+(nav.b>ul>li*4)+main.b+section.section1.b+section.section2.b+aside.b+footer.b`
* NOTE: After pasting, you might need to delete the last letter `b`, then re-type `b` so the emmet shortcut becomes available and can be selected, then press enter and the elements will be created
8. Add placeholder content inside the elements. Type the following text inside the specified elements
* `HEADER HEADER` in `header`
* `NAV LINK` in each of the 4 `li` tags
* `MAIN CONTENT` & `lorem100` in `main`
* `lorem50` in both `section` tags
* `SIDE BAR` & `lorem25` in `aside`
* `FOOTER` & `lorem20` in `footer`
9. NOTE: Below you will be instructed to paste css into the main.css file. After pasting, make sure to clean up the code so it is in the correct format. You could also use an extension like 'Beautify' to format your code.
10. Add below to main.css so you can see the element containers better:
* `.b {
    border: 1px solid black;
    border-radius: 5px;
    background-color: rgb(243, 173, 116);
    padding: .5em;
}`
11. Add below to main.css to make the div.wrapper set to use css grid:
* `.wrapper {
    margin: auto;
    display: grid;
    grid-gap: 15px;
    grid-template-areas: "header" "nav" "main" "section1" "section2" "side" "footer";
}`
* We will set the grid areas in the next step
12. Add below to main.css to name the grid areas so they respond to the `grid-template-areas` code in the `.wrapper` selector:
* `header {
    grid-area: header;
}`
* `nav {
    grid-area: nav;
}`
* `main {
    grid-area: main;
}`
* `.section1 {
    grid-area: section1;
}`
* `.section2 {
    grid-area: section2;
}`
* `aside {
    grid-area: side;
}`
* `footer {
    grid-area: footer;
}`
13. The webpage is now setup for mobile. All the elements are stacked on top of each other in the order that we set them in the `.wrapper` selector
14. Now we will add Media Queries `@media` to main.css to format the page to become responsive when the screen is larger
15. Paste below into main.css so when the screen width gets to 700px the webpage changes to a 2 column layout. When formated, you will notice how readable the grid template area code is. `grid-template-columns` specifies there will be 2 columns, and `grid-template-areas` lists 2 `grid-area` names per line with quotes around the whole line.
* `@media (min-width: 700px) {
    .wrapper {
        grid-template-columns: 1fr 3fr;
        grid-template-areas: 
            "header  header"
            "nav     nav"
            "side main"
            "side section1"
            "side section2"
            "footer  footer";
        }
        nav ul {
            display: flex;
            justify-content: space-around;
        }
    }`
* NOTE: Notice we also added some css to the `nav ul` so the nav links will show in a row instead of a column
16. Paste below into main.css so when the screen width gets to 1000px the webpage changes to a 3 column layout.
* `@media (min-width: 1000px) {
    .wrapper {
        grid-template-columns: 1fr 2fr 2fr;
        grid-template-areas: 
            "header header header"
            "nav nav nav"
            "side main main"
            "side section1 section2"
            "footer footer footer";
        }
    }`
