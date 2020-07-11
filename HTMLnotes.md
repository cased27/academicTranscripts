# HTML NOTES
This is a compilation of my notes about the basics of HTML.<br>
* it's the 'skeleton' of the page; no frills
* comment/comment out code: `<!-- ... -->`
* documents saved with ' .html ' in code editor
* must use ' index.html ' in order to create webpage with GitHub

#### TAGS
`<openingTag>` CONTENT `</closingTag>`

| TAGS                            | NAME              | DESCRIPTION                                            |
|---------------------------------|-------------------|--------------------------------------------------------|
| `<html>`...`</html>`            |                   | opening tags for doc                                   |
| `<!DOCTYPE>`                    |                   | required at top of doc                                 |
| `<head>`...`</head>`            | heading           | metadata goes here; these items do not appear on page  |
| `<title>`...`</title>`          | title             | name of page in tabs bar                               |
| `<body>`...`</body>`            | body              | all content goes here                                  |
| `<h1>, <h6> `...`</h1>, </h6> ` | header 1 ... 6    | organizes content via headings (font-sizes vary)       |
| `<p>`...`</p>`                  | paragraph         | organizes content via paragraphs (adds spacing)        |
| `<ol>`...`</ol>`                | ordered list      | numbered list items                                    |
| `<ul>`...`</ul>`                | unordered list    | bullet-point lists                                     |
| `<li>`...`</li>`                | list items        | used to add content within any list type               |
| `<strong>`...`</strong>`        | bold text         | make any specific text bold                            |
| `<u>`...`</u>`                  | underline text    | make any specific text underlined                      |
| `<em>`...`</em>`                | italicize text    | make nay specific text italics                         |
| `<div>`...`</div>`              | block container   | groups content together                                |
| `<span>`...`</span>`            | in-line container | groups content together w/o line break                 |
| `<table>`...`</table>`          | table element     | creates an HTML table                                  |
| `<th>`...`</th>`                | table header      | creates a table header (in bold)                       |
| `<tr>`...`</tr>`                | table row         | adds a new row to a table                              |
| `<td>`...`</td>`                | table cell        | adds a new cell to a table                             |
| `<thead>`...`</thead>`          | table 'header'    | organize `<th>`s                                       |
| `<tbody>`...`</tbody>`          | table 'body'      | organize `<tr>`s and `<td>`s                           |
| `<form>`...`</form>`            | form              | container for inputs (block element)                   |
| `<input>`...`</input>`          | input             | interactive controls; various 'types' (see attributes) |
| `<label>`...`</label>`          | label             | adds caption to inputs; can be nested in inputs        |
| `<button>`...`</button>`        | button            | adds any type of button to webpage                     |
| `<select>`...`</select>`        | select            | drop-down menu                                         |
| `<option>`...`</option>`        | option            | used w/ `<select>` tag                                 |
| `<textarea>`...`</textarea>`    | text box          | lrg text input box; adjustable size                    |
| `<link>`                        | link (CSS & HTML) | `<link rel="stylesheet" type="text/css" href="">`      |

------

#### ATTRIBUTES
* adds additional info or identifiers to tags
* `<tagName = "`<em>attribute</em>`"> ... </tag>` 
* note: some tags are <em>self-closing</em> (meaning they do not require a closing tag)

| TAGS                              | NAME               | DESCRIPTION                                            |
|-----------------------------------|--------------------|--------------------------------------------------------|
| `<img src="">`                    | image              | adds image                                             |
| `<a href="">...</a>`              | anchor tag w/ link | in-line element; adds webpage link                     |
| `<p class="">`                    | class              | adds a class                                           |
| `<input type="text"></input>`     | text input         | adds a textbox                                         |
| `<input type="date"></input>`     | date input         | adds a 'date' selector                                 |
| `<input type="color"></input>`    | color input        | adds a color selection                                 |
| `<input type="file"></input>`     | file input         | adds a 'choose file'                                   |
| `<input type="checkbox"></input>` | checkbox input     | adds a checkbox option (select/deselect)               |
| `<input type="radio"></input>`    | radio input        | adds a radio button (circular; cannot be deselected)   |
| `<...name=""></name>`             | name               | identifier for http request                            |
| `<...value=""></value>`           | value              | adds a value fo http 'name' attribute                  |
| `<input placeholder="">`          | placeholder input  | adds placeholder text (for instructions)               |
| `<form action=""></form>`         | action             | where URL sends form data TO                           |
| `<form method=""></form>`         | method             | type of http request ('get' or 'post' requests)        |
| `<label for=""></label>`          | for                | connects the tag (ex 'label') to input *!accessibility |
| `<input id="" required></input>`  | required           | requires an input to be filled                         |
| `<input pattern="(5,10)">`        | pattern            | adds requirement b/tw 5-10 characters (for passwords)  |
| `<input required title="">`       | title (required)   | response if required field is not completed            |
| `<input type="checkbox" checked>` | checked checkbox   | auto-check a checkbox upon opening pg                  |
| `<...id="">`                      | ID                 | unique identifier to target element (1x/pg)            |
| `<...class="">`                   | class              | applies style to any tag w/ same class                 |