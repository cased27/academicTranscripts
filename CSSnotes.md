# CSS NOTES
This is a compilation of my notes about the basics of CSS.<br>
* this is the 'skin' of the page; it gives it style
* comment/comment out code: `/*...*/`
* documents saved with ' .css ' in code editor

#### 
>Selector { <br>
>>property1: value; <br>
>>property2: value; <br>
}

| SELECTORS                     | DESCRIPTION                                      |
|-------------------------------|--------------------------------------------------|
| background-color color;       | sets background color                            |
| background: URL;              | sets background URL/image                        |
| background-repeat: no repeat; | sets background to single image                  |
| background-size: cover;       | sets background to cover entire webpage          |
| border: width, color, style;  | sets border to background (3-in-1; can separate) |

<br>

| PROPERTIES                  | NAME             | DESCRIPTION                                                            |
|-----------------------------|------------------|------------------------------------------------------------------------|
| #name{...}                  | ID selector      | selects an element w given ID                                          |
| .name{...}                  | Class selector   | selects an element w given Class                                       |
| div {...}                   | element selector | selects a given element                                                |
| *{...}                      | star             | applies to all elements (not common)                                   |
| tagName tagName{...}        | decendents       | all elements w/in tag (li a{...} = all anchor tags w/in `<li>`         |
| tagName + tagName{...}      | adjacent         | all elements after element (p + ul{...} = all `<ul>` children in `<p>` |
| input[type="checkbox"]{...} | attribute        | all similar-named attributes (all checkbox attr)                       |
| :nth-of-type(){...}         | nth of type      | selects every nth-numbered item an assigns specific style              |
| ul:nth-of-type(3){...}      |                  | selects 3rd `<ul>` to apply special style                              |
| li:nth-of-type(even){...}   |                  | selects every even `<li>` to apply special style                       |

<br>

------

<br>

#### COLORS

<u>Hexadecimal</u> (blend of 0-9 & A-F): ‘#’ + string of 6 hexadecimal numbers (0-F) (ex: #000000 is black, #FF1493 is pink). 
In a hexadecimal number each position represents how much color is in each place. The first 2 numbers correspond to how much RED is in the color, the second 2 numbers correspond to how much GREEN is in the color, and the last 2 numbers correspond to how much BLUE is in the color. (#RRGGBB) For ex: 

* #FF0000 will turn RED to max (F is the highest value) and leave GREEN and BLUE at 0

Use a color picker (online, google), find the color you want, and copy-paste onto your code 

<u>RGB</u> has 3 channels: RED, GREEN, BLUE and ranges from 0-255 (for ex: rgb(0, 255, 0) will give you GREEN because RED is 0, GREEN is at max, and BLUE is at 0. 

* rgb(0, 0, 0); is BLACK   //  rgb(255, 255, 255) is white 

<u>RGB<strong>A</strong></u> has 4 channels (the 4th is an alpha (transparency) channel that ranges from 0.0-1.0). 

* rgba(11, 99, 150, 1) will be a BLUE color, rgba(11, 99, 150, .2) is a BLUE color that is very faded 

<br>

#### FONTS

Font-Family: determines which font your text will be. Using a website (css font stack or google fonts) is helpful to see different font options as well as which fonts are typically compatible with diff servers 

Font-Size: determines the size of the font 

* px (pixels) will establish a set font size (static; not responsive)

* em: this sizing is dynamic/ relative. It is equal to the size of the font that applies to the parent of the element in question (ex: applying a 2.0em to a `<span>` element within a `<p>` element will double the font size for the `<span>` element compared to the font size of `<p>` 

Font-Weight: how bold or thick the text/font is (can select “bold”, “normal”, or a numeric value (100-800, only selectable in 100’s) for certain fonts. 

Line-height: controls the height of a given line (spacing between text line-to-line) 

Text-align: controls how the text of a given element is aligned (left, right, or center) 

Text-decoration: adds effects to the text itself (underline, line-through, etc) 

<br>

#### The Box Model 

In a doc, each element is represented as a rectangular box. In CSS, each of these rectangular boxes is described using the standard box model. Each box has 4 edges: margin-edge, border-edge, padding-edge, and content-edge (from outside-in) 

* These can be set (similar to “border”) as an all-in-one (i.e. margin: 20px 40px 500px 100px which would apply each size clockwise starting at the top) OR you can write each side individually (i.e. margin-top: 20px, margin-right: 40px, ...) 

* Margin: auto; will auto center/align the elements (can be margin: 0 auto; which will set the top and bottom to 0 and the left and right to auto) 