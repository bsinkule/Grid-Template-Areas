# CSS Grid Template Areas - Step by Step

## Objective
In this walk-through you will be pasting css code into the main.css file which will demonstrate how easy it is to use CSS Grid Template Areas to make a responsive web page layout.

## Steps
1. Fork and clone this repo
2. In your terminal, `cd` into the folder
3. In your terminal, run `lite-server`
4. Open the folder in your code editor. 
5. First, open the HTML page and inspect the layout. The main things to notice are that there is a `<div class="wrapper">` element which is the parent (i.e. wrapper) of `header`, `nav`, `main`, 4 `section` elements/containers, `aside` and the `footer`. Later we will assign those child elements `grid area` names, which will be the reference that the `grid-template-areas` code will reference and use to lay out the page.
6. If you look at the site in your browser now, you'll notice it looks pretty cluttered. Add the below code to main.css so you can see the element containers better in the browser. The `border` and `background-color` make it easier to see each container:
```css
.b {
    border: 1px solid black;
    border-radius: 5px;
    background-color: rgb(243, 173, 116);
    padding: .5em;
}
```
12. Add the below code to main.css to name the grid areas so they respond to the `grid-template-areas` names in the `.wrapper` selector that we will add after this code:
```css
header {
    grid-area: head;
}

nav {
    grid-area: nav;
}

main {
    grid-area: main;
}

.section1 {
    grid-area: section1;
}

.section2 {
    grid-area: section2;
}

.section3 {
    grid-area: section3;
}

.section4 {
    grid-area: section4;
}

aside {
    grid-area: side;
}

footer {
    grid-area: footer;
}
```
11. Add the below code to main.css to make the `<div class="wrapper">` element set to use css grid. This can now use all the grid-area named elements we just specified above. 
We will start by making a mobile layout that will ba a one column layout. The `grid-template-columns` specifies this by just listing parameter, `100%`. If there were two parameters, like `60% 40%`, that would specify a two column layout as you will see later.  :
> NOTE: 
```css
.wrapper {
    margin: auto;
    display: grid;
    grid-gap: 15px;
    grid-template-columns: 100%;
    grid-template-areas: 
        "head" 
        "nav" 
        "main" 
        "section1" 
        "section2" 
        "section3" 
        "section4" 
        "side" 
        "footer";
}
```
> NOTE: By listing each individual grid area (e.g "header" "nav" "main" etc.) with quotes around each name, we are setting up our mobile layout first where each element will be stacked in one column. We will adjust for other screen sizes in steps 15 and 16.

13. The webpage is now setup for mobile. All the elements are stacked on top of each other in the order that we set them in the `.wrapper` selector. Check it out in the browser.
14. Now we will add Media Queries `@media` to main.css to format the page to become responsive when the screen is larger
15. Paste the below code into main.css so when the screen width gets to 700px the webpage changes to a 2 column layout. When formated like in the image below, you will notice how readable the grid template area code is. `grid-template-columns` specifies there will be 2 columns (the left column is 1fr (i.e. 25%) and the right will be 3fr (i.e. 75%)). The `grid-template-areas` lists 2 `grid-area` names per line with quotes around the 2 `grid-area` names to show what elements will be in each of the 2 columns. This will be more evident when you look at the page in the browser.
```css
@media (min-width: 700px) {
    .wrapper {
        grid-template-columns: 1fr 3fr;
        grid-template-areas: 
            "head  head" 
            "nav     nav" 
            "side    main" 
            "side    section1" 
            "side    section2" 
            "section3 section3"
            "section4 section4"
            "footer  footer";
    }
    nav ul {
        display: flex;
        justify-content: space-around;
    }
}
```
> NOTE: Notice we also added some css to the `nav ul` so the nav links will show in a row instead of a column like in the mobile layout

16. Paste the below code into main.css so when the screen width gets to 1000px the webpage changes to a 3 column layout.
```css
@media (min-width: 1000px) {
    .wrapper {
        grid-template-columns: 1fr 2fr 2fr;
        grid-template-areas: 
            "head   head   head" 
            "side   nav    nav" 
            "side   main   main" 
            "side  section1 section2"
            "section3 section3 section4" 
            "footer footer footer";
    }
}
```

## Conclusion
* I hope this helped show how easy it can be to use CSS Grid Template Areas to achieve responsive layouts that will look good on mobile phones, tablets, laptops and desktops.
* I recommend using Flexbox to style the content-elements (i.e. `p`, `img`, `a`, etc.) that you put inside your grid area elements, as we did with the `nav ul` in the 700px media query. 
* Play around with the design. You could easily add in more sections, or make a 4 column layout for desktops that includes a right side bar for advertising. The possibilities are endless. Enjoy!