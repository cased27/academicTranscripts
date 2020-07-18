# BOOTSTRAP 

Most popular HTML, CSS, and JS framework for developing responsive, mobile first projects on the web 

In essence it’s a single CSS file and a single Javascript file; like a bin of lego pieces that you can add to your site as you see fit 

* Must always be inside a `<div class=”container”></div>` AND must always have a `<div class=”row”></row>`

    * Containers take up 12 parts and can be divided using these 12 parts as a base 
    * Ex: grouping 6 parts together you would get 2 columns or parts; grouping 4 parts together will produce 3 columns/ parts; you can group 2, 8, 2 (whatever way that adds up to 12) 

        `<div class=”container”> ` <br>
        `<div class=”row”>` <br> 
        `<div class=”col=lg-6">COL LG 6</div>` <br> 

    * 4 sizes: XS (xs: mobile layout) S (sm: tablet layout) M (md: laptop/desktops) L (lg: large desktop) which correspond to the pages’ responsiveness to diff screen sizes 

* **Add 70px of padding to <body> to adjust top spacing when using a fixed navbar 

<ins>BOOTSTRAP V3 </ins>

Must always add in the required `<link>` and/or `<script>` for Bootstrap CSS, Javascript, and JQuery (if required). You can check the requirements by “inspecting” the page and seeing any error codes 

* Adding Bootstrap to HTML doc:  

    * google search “Bootstrap CDN” (make sure to request the correct version you want to work with) 
    * Copy the link provided for CSS and Javascript in Bootstrap (*correct version) 
    * The CSS link should go in the `<head>` of the HTML doc in a `<link>` tag. This is the link for Bootstrap CSS 3.3.5 (not the most up-to-date) <br> 
    `<link rel="stylesheet" type="text/css" href="https://stackpath.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css"> `
    * The Javascript link should go in the bottom of the `<body>` of the HTML doc in a `<script>` This is the link for Bootstrap Javascript 3.3.5 (not the most up-to-date) <br>
    `<script type="text/javascript" src="https://stackpath.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js"></script>` 

    * If JQuery is required you can google search JQuery CDN and copy the link of the correct version. The JQuery link should be added to the bottom of the `<body>` tag but above the Javascript tag (or else the doc will not read it). It should be in a `<script>` tag. This is the link for JQuery 2.2.4 (not the most up-to-date) <br>
    `<script src="https://code.jquery.com/jquery-2.2.4.min.js" integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44=" crossorigin="anonymous"></script>` <br> 
    First you make a `<script>` tag and then add src=”URL” inside the tag 

* Adding Bootstrap3 Navbar to HTML doc 
    * Go to Bootstrap and select version you want to use. After correct version is selected, go to components (top navbar on homepage) and select “Navbar” on the right side menu bar 
    * Select and copy all of the “nav” code and paste into top of `<body>`  tag in HTML doc 
    * *not all of the code will be used but it’s best to start with the whole code and edit here and there where needed to get the desired result 

 

<ins>BOOTSTRAP V4 </ins>

General

* Add class=”active” to an `<li>` (for example) to make it “selected” or grayed out background <br>
(for example add the active class to “Home” `<li>` for a navbar and it will gray out the “Home” btn 

* Add class=”disabled” to a `<button>` (for example) on the navbar to make it “deselected” or grayed out 

* Always check out BS homepage for all the details on how to use the code 

Adding Bootstrap4 to HTML doc 

* Go to Bootstrap website and click “Get Started”. On the LEFT menu bar you have all the different selections and items that are available with code details within each topic 

* There is an additional JS tag that needs to be added to BS4 in order for it to work properly. BEST PRACTICE is to copy-paste the entire “Starter Template” available (scroll down) on the Intro pg of Getting Started. 

* Each item in the LEFT menu bar has different topics to select from to retrieve code that can be copy pasted to your HTML doc / CSS 

Notable Changes from BS3 to BS4 <br> 
(The biggest differences are the additions to BS4 that were not available on the prev versions)

* `Display (1)` is used for larger/diff headings in ‘typography’ and (2) for showing or hiding content on screen sizes (in Utilities-Display) 

* Hidden/Visible (V3) NOW `d-value` or `d-breakpoint(size)-value` (V4) are a way of changing the display property of something (having something be hidden on smaller screens or appear on larger screens) 
    * Great to hide/show images, icons, or text (on Jumbotrons for ex) on diff screen sizes 
    > `{value}= none | inline | inline-block | block | flex | inline-flex |` etc  

    `<h1 class= “border border-danger d-inline">` <br>
    would read as h1 with a default border, color ‘danger’, and instead of being a block level element this one will be an inline element <br>
    
    `<h1 class= “d-xl-none">` <br>
    would show on all smaller screens but disappear at XL screens <br>
    
    `<h1 class= “d-none d-lg-block">` <br> 
    would not show as a default but will appear on the LRG screen size (or larger). if you added `d-xl-none` then it would disappear again on the XL screen size. Useful for Jumbotrons (for ex) to hide too much info on smaller screens <br>
    
    `<p class= “lead d-none d-md-block">` <br>
    would have the `<p>` element not show as a default. It will only appear on MED screen sizes (or larger) as a block element 

* Navbars (smaller and larger nav bars (and notation) 

* Collapsing/expanding navbars at selective screen sizes (EX:) 
`<nav class= “navbar navbar-expand-lg">` will only expand the navbar when its in the LRG screen size (XS, SM, MED will all have the ‘hamburger’ menu collapsed) 

* Colors: can be added to the navbar (navbar-light or navbar-dark) and background colors (no background color by default; bg-light, bg-info) 

* Borders (adding, subtracting, colors, etc) 

* Colors & backgrounds (using ‘info’ ‘warning’ ‘danger’ color classes with text-danger or border-danger to add color to each aspect) 

* Spacing - Padding/margin (shorthand version adding property, sides, and size in 3 letters) 
    * Property: P (padding) or M (margin) 
    * Side: T (top) B (bottom) L (left) R (right) X (left &right) Y (top &bottom) blank (all) 
    * Size: 0-5 (0= smallest and 5= largest) 
    * EXAMPLE: `<button class= “btn pt-4">` would translate as padding-top-4 `<p class=”mx-3">` would be margin-left-3 & margin-right-3 

* Responsive Breakpoints (for resizing screens/ using and have responsive code for smaller/ larger devices) *located in “layout” section, scroll down to “media queries” 
    * THE DEFAULT LAYOUT IS ALWAYS FOR THE XS SCREEN SIZE; TO ADJUST APPEARANCES, SET DEFAULT (FOR XS OR SM) AND ADD CAVEATS FOR LARGER SCREEN SIZES 
    * You can add classes/padding/margin, etc that is specific to a certain screen size 

    * Padding example:  
        `<button class= “btn btn-warning p-sm-5 p-md-0 p-lg-5 p-xl-4">` which would have a default button class, ‘warning’ color, when the screen is sized SM it will have 5 padding, when MED it will have 0 padding, when LRG it will have 5 padding, and XL it will have 4 padding (strange example but just to show the meaning) <br>

        `<button class= “btn btn-danger p-0">` means that unless told otherwise leave padding at 0 <br>

        `<button class= “btn btn-danger p-0 p-sm-2 p-md-3 p-lg-4 p-xl-5">` will default in xs as padding-0 and increase the padding with each size (from 2; the padding-1 is very small difference from padding-0) <br>

        `<button class= “btn btn-success p-0 pl-sm-5 pt-md-4">` will default in xs as padding-0 and change in SM to padding-left-5 and in MED to padding-top-4 and padding-top-4 

    * Margin Example: may be typical to keep items closer together on smaller screen and spread out in larger screens <br>

        `<button class= “btn btn-primary p-4 mx-0 mx-sm-2 mx-md-3 mx-lg-4 mx-xl-5">` will read as a button with default property, ‘primary’ color, padding-4 (all sides), default margin for L and R of 0 (in XS screen size), then in SM screensize L and R will have margin-2, MED screen size L and R will have margin-3, LRG screen size L and R will have margin-4, and XL screen size L and R will have margin-5 

 
**IF YOU WANT A CHANGE IN APPEARANCE/LAYOUT IN THE XS SCREEN SIZE YOU ALWAYS HAVE TO SET THE DEFAULT AND THEN OVERRIDE THE DEFAULT WITH A DIFF SIZE SPECIFIED 
 
<hr> 

<ins>GRID SYSTEM – RESPONSIVE GRID </ins>

Most commonly used feature in Bootstrap 

The Grid System works with ROWS (same as BS V3) which are divided up into 12 columns. You can adjust and change the use/size/etc of these columns as desired (depending on the screen size) 

There are now 5 column sizes: XS SM MD LG XL 
* *S was redefined with smaller dimensions so all the sizes changed based on the XS dimensions (i.e. all breakpoints have been shifted) 
* XS is the default defined size and you adjust responsive design in all larger dimensions 

Examples:  

`<h3 class=”col-6”></h3>`  <br>
`<h3 class=”col-6”></h3>` <br>
reads: occupy 2 equally sized columns (6/12 parts) on 1 row in all sizes (*this is not responsive) 

`<h3 class=”col-sm-6 col-xl-3"></h3>` <br>
`<h3 class=”col-sm-6 col-xl-9"></h3>` <br> 
reads: in XS stay stacked (i.e. NO columns 0/12). At SM size (and above) split into 2 even columns (each occupying 6/12 parts). Then only at XL: the first h3 occupies 3/12 parts and the second h3 occupies 9/12 parts 

`<div class=”row”> ` <br>
`<div class=”col bg-primary"></div>` <br>
`<div class=”col-6 bg-info"></div>` <br>
`<div class=”col bg-success"></div>` <br>
`</div>` <br>
(adding just the ‘col’ class without parameters will evenly auto-distribute the space of all col defined) Reads: always apply size of 6/12 for background-info div, then always evenly distribute the rest of the space between background-primary and background-success 