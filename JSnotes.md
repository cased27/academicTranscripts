# JAVASCRIPT

* JS is the 'verb' of a webpage 
* comment out using `//` (double slash)
* clear the console using the function `clear()`
* 'inspect' the page and use the console (developer's tool)
* docs are saved with ' .js ' 


<a name="tableOfContents" class="tableOfContents"></a>

### <ins>TABLE OF CONTENTS</ins>
There are a lot of notes on JS! Click any of the links below to jump to any particular topic

- [Getting Started in the Code Editor](#getStarted)
- [Primitive Datatypes](#pDatatypes)
- [Variables](#variables)
- [Methods](#methods)
- [Conditionals](#conditionals)
- [Loops](#loops)
- [Functions](#functions)
- [Arguments](#arguments)
- [Arrays](#arrays)
- [Objects](#objects)
- [DOM](#dom)

<hr>
<a name="getStarted" class="getStarted"></a>

### GETTING STARTED IN THE CODE EDITOR 
IDE: (Integrated Development Environment / Code Editor) communicate commands to the console w/o having to do so directly

1. Open and create an HTML file, save `docName.html`
2. Open and create a Javascript file, save `docName.js` in same folder/location as html file 
3. Link the HTML & Javascript files `<script src=”docName.js”></script>` 
	* Location on the HTML doc: changing the location will change the order of operations for the webpage as it loads 
	* If it’s in the `<head>` below `<title>` in the HTML doc all JS will load first, then HTML 
	* If it’s in the `<body>` below all the text then the HTML will load first, then JS

###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="pDatatypes" class="pDatatypes"></a>

### PRIMITIVE DATATYPES

Different categories of data

* [NUMBERS](#numbers): whole number (4) fraction (9.3) negative (-10); All numbers are treated the same 

* [STRINGS](#strings): words or numbers inside quotations (single or double) like "Hello World" or "43"

* [BOOLEAN](#boolean): either TRUE or FALSE 

* NULL: variables that are explicitly <em>nothing</em>
	* used often in games for 'game over' or the end
	<br>`var currentPlayer = “charlie”; `
	<br>`currentPlayer = null;` // game over 
				
* UNDEFINED: variables that are declared but not initialized/ defined; it’s a ‘nothing’ value but only because it hasn’t been declared <em>yet</em>
	* `var name;`  OR `var age;`
	<br>both undefined; they are declared but no value is assigned (like `var name = “Helen”`) (in the console you'd get ‘undefined’ because they have no value assigned to them) 

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="variables" class="variables"></a>

### VARIABLES

variables are containers to store values to be referenced later. 

* Format: `var yourVariableName = yourValue;`
* JS uses `camelCase` (there is also `snake_case` and `kebab-case`)

>strings: `var name = "dusty";` <br>
>numbers: `var secretNumber = 73;` <br>
>booleans: `var isAdorable = true;`

Recall the stored value by calling the variable name

> `"hello there " + name` // "hello there Dusty"

<br>
<ins>VAR vs LET vs CONST</ins><br>
General Rule: use <strong>const</strong> over <strong>let</strong>, use <strong>let</strong> over <strong>var</strong>, use <strong>var</strong> as little as possible (likely only with legacy code)

* Var (variable) are scoped to the ‘current execution context’ (a variable’s enclosing function or the global scope) 
	* A variable can be reassigned whenever and redeclared at any point 
	* Initializing with value is optional 
	* Global variables are added to window 

* Let is block scoped 
	* It can be reassigned but it cannot be redeclared (within the same scope)  
	* Initializing w value is optional 
	* It does not create a property on global window object 

* Const (constant) is block scoped 
	* It cannot be reassigned (not immutable, but variable reference cannot change) and cannot be redeclared (in the same scope) 
	* It must be initialized with value 
	* It does not create a property on the global window object 

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="methods" class="methods"></a>

### METHODS

Adding a function as a property/value of an object 

* `alert()` pops up a message to the user in a pop-up window 
* `prompt()` can get input from the user 
	* `prompt(“what is your name?”);`  
	will send this question thru (with an answer box) in a pop-up window, allowing the user to answer. The answer will appear in the console 
* `console.log()` prints out whatever text is requested through the console (not on the page itself) 

<ins>KEYWORD “THIS” </ins>

A method (`this.`)added to objects in order to access/share pre-defined data. It's a common pattern to organize code: you take data, put it inside an object, then take associated functions and add them as methods to the same object and use the keyword THIS to access the data that was pre-defined 


<ins><a name="domMethods" class="domMethods">DOM Methods</a></ins> are used to select elements
1. `document.getElementById( )` allows you to call an element using it’s ID tag <br>
	>`var tag = document.getElementById(“enter ID name here”);` <br>
	calling the variable ‘tag’ will bring up the entire item (whether it’s an `<li>` or other element) that contains the ID of the name entered 

2. `document.getElementsByClassName( )` allows you to call an element using it’s CLASS tag <br>
	>`var tags = document.getElementByClassName(“enter ClassName here”);` <br> calling the variable ‘tags’ will bring up the entire item (whether it’s an `<li>` or other element) that contains the CLASS NAME of the name entered
	* Note ‘tags’ (plural) because there are more than one 
	* You cannot use .forEach here because this is a list, not an array  

3. `document.getElementsByTagName( )` allows you to call any element with the same tag name <br>
	>`var tags = document.getElementsByTagName(“enter TagName here”);` <br>
	calling the variable ‘tags’ will bring up a list (even if there is only one element) of every element with the same tag name (like `<li>, <h1>`) 

4. `document.querySelector( )` returns the first element that matches a given CSS-style selector 
	> `var tag = document.querySelector(“#enter ID name here”);` <br> 
	calling the variable ‘tag’ will bring up the first item (whether it’s an `<li>` or other element) that contains the ID of the name entered <br>
	`var tags = document.getElementByClassName(“.enter ClassName here”);` <br>
	calling the variable ‘tags’ will bring up the first item (whether it’s an `<li>` or other element) that contains the CLASS NAME of the name entered
	* Note that using `.querySelector` will give you an array 

5. `document.querySelectorAll( )` returns all the elements that match a given CSS-style selector <br>
	>`var tags = document.querySelectorAll(“h1”);` <br> 
	calling the variable ‘tags’ will bring all the h1 elements <br>
	`var tags = document.querySelectorAll(“.enter ClassName here”);` <br>
	calling the variable ‘tags’ will bring all the h1 elements 
	* Note that using `.querySelectorAll` will give you an Node list

###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="conditionals" class="conditionals"></a>

### CONDITIONALS

Making decisions with code *the most important element to learn to code 

<ins>Conditional statements:</ins> 

1. IF statements 
2. ELSE IF statements <br> 
(must follow an IF statement; they function the same as an IF statement so it’s like a continuation of the IF statement) 
3. ELSE statements 

Conditionals are made in conjunction with Boolean logic and they work in order (from first code to last). Examples: 

> If you are younger than 18, you cannot enter the venue <br>
> If you are between 18 and 21 you can enter but cannot drink <br>
> Otherwise, you can enter and drink 

>`if(age < 18) {` <br>
 `console.log(“sorry, you are not old enough to enter the venue”)}` <br> 
 `else if(age < 21) {` <br> 
 `console.log(“you can enter, but cannot drink”)}` <br> 
 `else { ` <br>
 `console.log(“come on in and drink!”)}`

*Notes: 

`<prompt>` always returns a string; there are many ways to convert strings into numbers (research) but one way is to insert `Number(prompt(…));` 

`Math` is a built-in object that has properties and methods for mathematical constants and functions; it works with the Number type (*must be capital 'M')

To find odd/even numbers, or square roots, etc use MODULO`(%)` and Math `(Math.sqrt)`


###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="loops" class="loops"></a>

### LOOPS

Loops are a way to condense code that is doing the same thing over and over again, i.e. rapidly complete repetitive tasks 
* Counter: is the starting point of a loop 
* Exit condition: criteria under which the loop stops (usually when it reaches a certain value) 
* Iterator: generally increments the ‘counter’ by a small amount on each successive loop until reaching the exit condition 

DRY: Don’t Repeat Yourself; always keep your code as DRY as possible for time-saving and clean code 

1. WHILE LOOPS: repeats code WHILE a condition is True. It's very similar to an IF statement except an IF statement will run the code one time, a WHILE LOOP will repeat a given code block while a condition remains True 

	* Ex: printing numbers 1-5 <br>
	`var count = 1;` <br>
	`while(count<6)` <br>
	`{console.log(“count is: “ + count); count++;}` 

	* ++ will add 1 to each number in succession 
	* +=2 will add 2 to each number in succession 

		* Ex: printing each character in a string <br>
	`var str = “hello”;` <br>
	`var count = 0;` <br>
	`while(count < str.length)`<br> 
	`{console.log(str(count)); count++;}` <br>
		this will read as: “the string is defined as “hello” and the count starts at 0; while the count is less than the length of the string, add 1 to each count number for the letter of the string 

	* Infinite Loops: occur when the terminating condition in a loop is never False *you NEVER want this to happen! 

		* Example: <br>
		`var count = 0;` <br>
		`while (count < 10)`  
		`{console.log(count);` <br>
			this will read as: “count is = 0, while count is less than 10, console.log count.” But count is ALWAYS less than 10 since it isn’t being incremented, it will run an infinite loop 

	* `.indexOf()` returns the first index at which a given element can be found in the array, or –1 if not found. In WHILE LOOPS it allows you to expand the scope of the user answer <br>
		* Ex: adding an `.indexOf(“yes”)` to the annoy-o-matic will allow the user to answer “yes” or “yes we are” or “yes we have arrived” and because the `.indexOf(“yes”)` any answer that includes the word “yes”, even if it also includes more words than that, will complete the alert (and end the loop) 

2. FOR LOOPS: another way of repeating code; typical to use short/ one-letter variables like “i” instead of “count” 
the format always has 3 parts like this: for(initialize; condition; step) { … } 

	* For ex: printing numbers 1-5 

	* For Loop: below you can see the initialize value is var count = 0, the condition is count < 6,  and the step is count++. It is a more condensed version of the while loop below this example. NOTE: the variable is only declared within the loop 

		`for(var count = 0; count < 6; count++) {…}`

	* While Loop: this version is more drawn out and lengthy BUT as you can see the variable is not exclusive to the loop and must be declared outside of the loop <br>
		`var count = 1;` <br> 
		`while(count < 6) {` <br>
		`console.log(“count is: “ + count);` <br> 
		`count++; }` <br>

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="functions" class="functions"></a>

### FUNCTIONS

Allows us wrap bits of code into reusable packages. They are one of the building blocks of JS 

> `Function doSomething() {` <br> 
  `console.log(“Hello World”); }` <br> 

Then you call the function code: 

> `doSomething();` <br> 

Note: you can refer to a function `doSomething` which will just give you back the original function code that was written (it will not run the code it will just reveal what code was written in the console. In order to run the code you have to have the parenthesis and semicolon like this: `doSomething();` 

* Ex: Twinkle Twinkle Little Star Song: instead of having to repeat the same code over and over again (writing many repeating console.logs which would not be DRY) every time you want the song sang you can write a function and then call the function whenever you want it sung: 

>`function singSong() {` <br>
  `console.log(“Twinkle, twinkle, little star,”);` <br>
  `console.log(“How I wonder what you are!”);` <br>
  `console.log(“Up above the world so high,”);` <br>
  `console.log(“Like a diamond in the sky.”);` <br>

>`singSong();` <br> 
`singSong();`  

Calling the function `singSong();` twice (as above) will sing the song twice w/o rewriting each line 

Note: `clear()` is a function to clear the console 

* <ins>Return Keyword:</ins> add an input into a function and it will produce an output (INPUT > FUNCTION > OUTPUT) <br>
Without the return keyword you are getting a 'temporary’ response from the console.log. The information or code that is inputted is not being stored to be used elsewhere 

	`Function square(x) {` <br>
	`console.log(x * x); }` <br>

	`Square(4);    //16` 

	the response is only being console.logged; it is not able to be recalled again. In the console, the console.log will always return “undefined” unless a return has been specifically identified. 

	By using the return keyword you can in essence ‘save’ the information in the console to be recalled. You are able to ‘send’ information/code outside of a function and use it in other code within the console 

	`Function square(x) {` <br> 
	`return x * x;` <br>

	`Square(4);     //16` <br> 

	This response is being stored/saved within the console so it can be recalled in other code within the console, like within a string or other code. Without the return, a console.log alone cannot be recalled later in other code since it would be identified solely in the confines of the console.log function. So now I could write the following and the console would be able to recall the function above to use in the code: 

	`Var result = square(104);` 

	`Result     //10816` 

	In this case the function of square was recalled in the variable, the numbers computed (i.e. the square of 104), and stored in the variable called “result”; Result now stores the value of 10816 

	By using a return you are stopping/ ending the execution of a function. i.e. once the return keyword is executed the function will stop running. 

* Syntax to declare a function (there are 2) 

	1. Function Declaration: you have a function, the name of the function, pass in arguments, and pass in the body of the function within the {} brackets 

		`Function capitalize(str) {` <br>
		`return str.charAt(0).toUpperCase() + str.slice(1); } `

	2. Function Expression: set a variable which is set equal to a function; with this way, if you redeclare/ 

		`Var capitalize = function(str) {` <br> 
		`return str.charAt(0).toUpperCase() + str.slice(1); } `<br>

<ins>NAMESPACING</ins>
You can add a function with the same name if you identify each object of the function in a different way: <br>

>`function speak( ) {` <br> 
  `return “WOOF!”; }` 

>`function speak( ) {` <br> 
  `return “MEOW!”; } `

> `var dogSpace = { };` <br> 
`var catSpace = { };` <br> 

>`dogSpace.speak( ); ` <br>
`catSpace.speak( ); `

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="arguments" class="arguments"></a>

### ARGUMENTS

Arguments are how to write functions that take inputs/ values; they are mutable and changing based on information provided. It's more than just repeating code because you can add new info/ change. A FB profile page has arguments that use the imputed data from the user.<br>
> 	`Function square(num) {` <br> 
  	`console.log(num + num); }` <br>
	`square(10);    //100 ` <br>
	`square(4);     //16 ` 

Functions can take multiple arguments at a time: <br>
(for a site that has to check credentials, you might add in multiple bits of info, like an email and password, which the code would have to check and then allow or deny access) 

>`function area(length, width) {` <br> 
`console.log(length * width); }` <br> 
`area(9,2);     //18` <br>


###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="arrays" class="arrays"></a>

### ARRAYS

an array is a way to group data in a list

* You can call each item in an array by calling the index <br>
`var something =[thing1, thing2, thing3...]` <br> 
thing1 is at index 0, thing2 is at index 1, etc. 

* Empty arrays can be initialized in 2 ways <br> 
`Var friends = [];`     //no friends <br>
`Var friends = new Array();`     //uncommon way 

* Arrays can hold any type of data (numbers, stings, etc) <br> 
`Var random_collection = [49, true, “Hermione”];` 

* Arrays have a length property <br>
`Var nums = [45, 37, 89,, 34];` <br>
`nums.length      //4` 
 

1. PUSH: adds an item to the end of an array 
	`Var colors = [“red”, “orange”, “yellow”];`<br> 
	`colors.push(“green”);` <br> 
	// [“red”, “orange”, “yellow”, “green”] 

2. POP: removes an item from the end of an array 

	`Var colors = [“red”, “orange”, “yellow”];` <br> 
	`colors.pop();` // [“red”, “orange”] <br>
	`pop();` // returns the removed element <br>
	`var col = colors.pop();` // orange 

3. UNSHIFT: adds an item to the front of an array 

	`Var colors = [“red”, “orange”, “yellow”];` <br> 
	`colors.unshift(“infarared”)` <br> 
	// [“infarared”, “red”, “orange”, “yellow”] 

4. SHIFT: removes an item from the front of an array 

	`Var colors = [“red”, “orange”, “yellow”];` <br> 
	`colors.shift();` // [“orange”, “yellow”] <br>
	`Shift();` returns the removed element <br>
	`var col = colors.shift();` // orange 

5. IndexOf(): finds the index of an item in an array (it’s location in an array). Index starts at 0 

	`Var friends = [“Charlie”, “Liz”, “David”, “Matt”, “Liz”];` <br> 
	`friends.indexOf(“David”);` //2 (returns the first index at which an element can be found) <br>
	`friends.indexOf(“blue”);` //-1 (returns –1 if an element is not present) 

6. SLICE: use slice() to copy parts of an array 

	`Var fruits = [“banana”, “orange”, “lemon”, “apple”, “mango”];` <br> 
	`var citrus = fruits.slice(1, 3);` <br> 
	// [“orange”, “lemon”] (var citrus contains these 2 items) <br>
	//[“banana”, “orange”, “lemon”, “apple”, “mango”]  (var fruits contains all the items still) 

	Use slice to copy the 2nd and 3rd fruits in the list (which are in index 1 and 2 respectively). However, when using slice, you have to indicate where the slice starts and where it ends. In the above example, the slice starts at index 1 (where “orange” is located) and ends at index 3 (where “apple” is located). So you would call index 1 and 3 in order to slice the items “orange” and “lemon”. 

<ins>ITERATION</ins> (commonly seen in pages w comments): using loops and forEach to iterate over an array 

* Loop 
* ForEach: `arr.forEach(someFunciton)` 

	`var colors = [“red”, “orange”, “yellow”, “green”];` <br> 
	`colors.forEach(function(color){` <br> 
	`console.log(color);` <br> 
	`});` <br>
	(note: ’color’ is a placeholder; can be named anything). <br>
  You are simply naming what each item in the array will be named and then calling each item in the console.log <br>
  Reads as "in the array 'colors' call each item 'color' and then console.log each color."

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="objects" class="objects"></a>

### OBJECTS

Objects store data in key-value pairs; they have no order (it’s not a list like an array). Think: dictionary... you look something up based on a key to get a corresponding value 

>`Var person = { ` <br>
  `name: “Travis”,` <br> 
  `age: 21,` <br> 
  `city: “LA” ` <br>
`}; ` <br>

* note the curly braces `{ }` are used instead of the square braces `[ ]` like in an array 

* Each element in stored under the key-value (in this case it’s ‘name’, ‘age’, ‘city’) 

* Objects can hold all sorts of data (strings, numbers, etc) just like arrays 

* To retrieve the data you can use bracket notation or dot notation 

	`Console.log(person[“name”]);` 
	`Console.log(person.name);` 

	* You cannot use dot notation if the property starts with a number <br>
		`someObject.1blah` //INVALID <br>
		`someObject[“1blah”]` //VALID 

	* You cannot use dot notation for property names with spaces <br>
		`someObject.fav color` //INVALID <br>
		`someObject[“fav color”]` //VALID 

	* You can lookup using a variable with bracket notation <br>
		`Var str = “name”` <br> 
		`someObject.str` //DOESN’T EVALUATE OR LOOK FOR “NAME” <br>
		`someObject[str]` //EVALUATES STR AND LOOKS FOR “NAME” 

* Just like an array, access a property to reassign it or edit/change it <br> 
	`person[“age”] += 1;` <br>
	`Person.city = “London”;` <br> 
	`dog.age = 6;`     //this will add the key “age” to the object 

* Just like an array, there are a few methods of initializing objects 
	* Make an empty object and then add to it <br>
		`Var person = { }` <br> 
		`person.name: “Travis”,` <br> 
		`person.age: 21,` <br>
		`person.city: “LA”;` <br>

	* Add all the data at once (object literal notation, as seen in the initial ex for ‘objects’) <br>
		`Var person = {` <br> 
		`name: “Travis”,` <br> 
		`age: 21,` <br>  
		`city: “LA” ` <br>
		`}; `

	* Make a ‘newObject’  
		`Var person = new Object(); `<br>
		`person.name: “Travis”,` <br>
		`person.age: 21,`  <br>
		`person.city: “LA”; `

###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="dom" class="dom"></a>

### DOM

Document Object Model is the interface between Javascript and HTML + CSS 

* <em>Select</em> an element and then <em>manipulate</em>
> Ex: select `h1` and then manipulate (change color from black to pink) <br> 
`var h1 = document.querySelector(“h1”)` <br>
`h1.style.color = “pink”;` 

See [DOM Methods](#domMethods) section for more info on DOM Methods

<ins>MANIPULATION</ins> 

1. Style: you can use the style property to manipulate an element's style 
	- Separation of Concerns: it's recommended for styles to be defined in a separate file(s). The style property allows for quick styling, for example for testing purposes 
	- There are 3 basic parts to a webpage: Structure, Behavior, Presentation. They overlap slightly in some areas but it is a generally accepted rule that each part is responsible for it's own contribution to the page (i.e. CSS is for styling, HTML is for stucture/ skeleton, Javascript is for function (VERB). 

		`var tag = document.getElementBy Id("highlight");` <br> 
		`tag.style.color = "blue";` <br> 
		`tag.style.border = "10px solid black";`<br>  

2. Text & Content:  
	- textContent: returns a string of all the text contained in a given element <br>
	`<p>Hello <strong>World</strong></p> ` <br>
	`var tag = document.querySelector("p");` <br> 
	`tag.textContent ` <br>
	//"Hello World" <br> 
	*note it only returns the content, not the `<strong>` tag inside <br>

		`tag.textContent = "blahblahblah"` <br>
		//this will change the `<p>` to "blahblahblah" 

 	- Be careful overwriting with `.textContent` because it will change/ remove parts inside the content (i.e. in the above ex if you wrote "Goodbye World" it would also remove the `<strong>` tag) 

 	- **use `.innerHTML` as an alternative option to be able to select more specific tags. It will return everything as a string including the inside HTML elements 

	- You can write HTML (with tags etc) with .innerHTML and it will show on the page like normal HTML. However `.textContent` will not; it reads everything literally and does not read an `<h1>` tag (for ex) as an `<h1>`… 

3. Attributes: 

	`.getAttribute( );` <br>
	`.setAttribute( );` 

	`var link = document.querySelector("a");` <br> 
	`link.getAttribute("href");`     //"www.google.com" 
	`link.setAttribute("href", www.dogs.com);`     
	//`<a href = www.dogs.com> I am a link</a>` 

	`Var img = document.querySelector("img");` <br> 
	`img.setAttribute("src", "odie.png");` <br>
	//`<img src="odie.png");` 

<ins>EVENTS</ins> 

Events make things interactive (for ex clicking a button, hovering over a link, etc).  

* Process: first you select an element and then you add an event listener 

	"Listen for a click on this `<button>`" <br>
	"Listen for a hover event on the `<h1>`" 

`.addEventListener` is used very often and there are two parts: 

1. Type of event that you want to listen for 

2. The code you want to run when the event happens 

	Ex: display a message when a button has been clicked: 

	`<button>Click Me</button>` <br>
	`<p>No one has clicked me yet</p>` 

	`var button = document.querySelector("button");` <br> 
	`var paragraph = document.querySelector("p");` 

SETUP CLICK LISTENER 

`button.addEventListener("click", function() {` <br> 
`paragraph.textContent = "Someone clicked the button!"; });` <br>

You can have more than one 'listener' on an element 

###### |[Table of Contents](#tableOfContents)| 


<hr>
<a name="numbers" class="numbers"></a>

### NUMBERS & NUMERIC OPERATIONS

The JS Console can be used like a calculator
* different operations are possible ( + - * / )
* Order of operations / (PEMDAS) Parenthesis, Exponents, Multiplication, Division, Addition, Subtraction 

<ins>Modulo</ins>: also called the remainder operator or Modulus is represented by ' % '

* Ex: 10 % 3 will give you 1 
<br>(it will divide 10 into 3 and then just give you the remainder as the solution)
* 20 % 5 will give you 0 
<br>(because 20 goes into 5 evenly 4 times) 

* Used often to find odd/even numbers, etc 
<br>`if (x % 2 !=== 0)` would find ODD numbers (if a number modulus by 2 does not equal 0, you have an odd number. 
	* 42 % 2 is 42/2 which is 21 with no remainder (so modulo is 0) then the result is an even number.  
	* 21 % 2 is 21/2 which is 10 with a remainder of 1 (so modulo is not 0) you have an odd number. 

* Used in conjunction with the Math operator to find sq roots, etc (**Math must be capitalized in order to be recognized by the console) 
	* if (age % Math.sqrt(age) ===0) 
	<br> will produce only the sq roots of age 
	* 9 % Math.sqrt(9) === 0 
	<br>reads: “9 modulus the square root of 9, which is 3, results in no remainder then you have a perfect square (9/3 is 3, which means that if you divide a number by its own square root and you do not get a remainder, you have a perfect square)
 
###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="strings" class="strings"></a>

### STRINGS

Strings are all/any content within quotation marks 

Single or double quotes are OK (but they must match) 

* “hello world” OR ‘hello world’ are VALID 
* “hello world’ is INVALID; they need to match 
* “I can’t stop eating candy” is VALID; you can have a single quote within a double 
* ‘I can’t stop’ is INVALID; the console reads that the sting ends after can 

<ins>Concatenation</ins>: adding strings together 
* “hi” + “goodbye” = “higoodbye” 
* “hi” + “ goodbye” = “hi goodbye” (adding space before “ goodbye” 

<ins>Escape Characters</ins>: start with `\` (backslash) and allow you to add special characters 

* Adding `\` allows you to add special characters (like quotations that would normally be read by the console) without allowing the console to read it as something else 
	* “she said \”goodbye!\”” will produce: she said “goodbye!” 
	* “she said ”goodbye!”” will be INVALID 
* To add an actual backslash to the code you would do a double backslash 
“Hello world. \\” will produce: “Hello World. \” 

<ins>Length Property</ins>: every string has a length property, starts counting at 1 

* `“my favorite number is: 1234”.length` is 27 characters long (includes spaces)

* Access individual characters using `[ ]` and an index: it will call the particular position in a string of the number requested starting at “0” (so the first character is at 0) 

	* `“hello”[0]` will produce: “h” (requests/calls for the character in the  0-position) 

 	* `“hello”[4]` will produce: “o” (requests/calls for the character in the 4-position) 

	* Inputting `“The Beatles”[4]` will produce: “B” 

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="boolean" class="boolean"></a>

### BOOLEAN
These statements can be used to combine the initial T/F statement to create more complex statements that also evaluate to T/F 
<br>

<ins>Comparison Operators</ins> <br>
(in table, ex assumes x = 5)

| Operators | Name                           | Example   | Result |
|:---------:|--------------------------------|-----------|:------:|
|     >     | greater than                   | x > 10    | false  |
|    >=     | greater than or equal to       | x >=5     |  true  |
|     <     | less than                      | x < -50   | false  |
|    <=     | less than or equal to          | x <= 100  |  true  |
|    ==     | equal to                       | x == "5"  |  true  |
|    !=     | not equal to                   | x != "b"  |  true  |
|    ===    | equal to (value & datatype)    | x === "5" | false  |
|    !==    | not equal to (value & datatype | x !== "5" |  true  |

<br><ins>Double Equals v Triple Equals (== vs ===)</ins>

- == (double equal) performs type coercion
				- ex: var x = 5  //  x==”5” is TRUE <br>
				Here there is a number and a string. With the double equal JS will strip away the datatype and then compare the values to see if they are the same (it only cares that the core values are the same, not whether they are of the same datatype) 
				- General Rule: avoid using == as much as possible b/c there are odd exceptions
								- True == “1”  // true however this is only true in this case! (true == “12” // false) 
								- 0 == false  // true 
								- null == undefined // true 
								- NaN == NaN  // false 

- === (triple equal) no type coercion 
				- ex: var x = 5  //  x===”5” is FALSE <br>
				Here we have a number and a string. With the triple equal JS will keep and compare the datatype and the value and see if they are the same 
				- General Rule: always try to use === since it is more specific 

<br><ins>Logical Operators</ins> (assuming below x = 5 and y = 9)

| Operator | Name | Example            | Result | Explanation                  |
|:--------:|:----:|--------------------|:------:|------------------------------|
|    &&    | AND  | x < 10 && x !== 5  | false  | requires both sides to be T  |
|   \|\|   |  OR  | y > 9 \|\| x === 5 |  true  | requires 1 side to be T      |
|    !     | NOT  | !(x===y)           |  true  | gives the opposite of result |

<br><ins>Truthy / Falsy</ins> 

* Every value (even those that aren’t actually T or F are still inherently ‘truthy’ or ‘falsey’ when evaluated in the a boolean context 
* If you enter “hello” into the console, you will get “hello” in return. If you add boolean text, and enter !”hello” into the console, you will get false in return (now that you have entered the text in the context of boolean you will get a T/F, and in this case, !”hello” negates the “hello” so you get False; !!”hello” would double negate the “hello” so you would get “hello”=T, !”hello”=F, !!”hello”=T 
* Everything is ALWAYS TRUTHY (including negatives) except: 
	* false = false (*the string “false” is T) 
	* “” = False (empty string is F) 
	* null = False 
	* 0 = False 
	* NaN = False 
	* undefined = false 
* These inherent truths and falsehoods are specific to JS

###### |[Table of Contents](#tableOfContents)| 
<hr>
