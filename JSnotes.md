# JAVASCRIPT

* JS is the 'verb' of a webpage 
* comment out using `//` (double slash)
* clear the console using the function `clear()`
* 'inspect' the page and use the console (developer's tool)
* docs are saved with ' .js ' 

ES6 is the most up-to-date version of Javascript. One of the many newer additions include the arrow function (=>)

The `debugger` can be used to track the console, step-by-step, in your code. It helps illuminate where you are at in the code, what you are telling the console, and how it is being read. 

`typeof` (not camelCase) will determine the datatype of whatever is put after it   

* `typeof 99` // number   
* `typeof mystery` // "string"

REPL 'Read Evaluate Print Loop' is using the console to get immediate evaluation of code (great for testing, not for longer writing of code)

<hr>

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
	  `var currentPlayer = “charlie”; `
	  `currentPlayer = null;` // game over 
				
* UNDEFINED: variables that are declared but not initialized/ defined; it’s a ‘nothing’ value but only because it hasn’t been declared <em>yet</em>
	* `var name;`  OR `var age;`
	  both undefined; they are declared but no value is assigned (like `var name = “Helen”`) (in the console you'd get ‘undefined’ because they have no value assigned to them) 

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="variables" class="variables"></a>

### VARIABLES

variables are containers to store values to be referenced later. 

* Format: `var yourVariableName = yourValue;`
* JS uses & recommends `camelCase` (there is also `snake_case` and `kebab-case` but not conventionally used)

>strings: `var name = "dusty";`   
>numbers: `var secretNumber = 73;`   
>booleans: `var isAdorable = true;`

Recall the stored value by calling the variable name

> `"hello there " + name` // "hello there Dusty"

<ins>NAMING VARIABLES</ins>
* Naming variables never has to be short! It is better to be clear/expressive and the name should relate to whatever the variable is doing or will be doing in the result. 
* avoid naming variables that correspond to HTML elements; think of a good descriptive name that will avoid confusion for others and that doesn't identify as another element. 
* you cannot name different variable with the same name ('let' and 'const' cannot have same variable names)

  
<ins>VAR vs LET vs CONST</ins>  
General Rule: use <strong>const</strong> over <strong>let</strong>, use <strong>let</strong> over <strong>var</strong>, use <strong>var</strong> as little as possible (likely only with legacy code)

* Var (variable) are scoped to the ‘current execution context’ (a variable’s enclosing function or the global scope) 
	* A variable can be reassigned whenever and redeclared at any point 
	* Initializing with value is optional 
	* Global variables are added to window 

* Let is block scoped 
	* It can be reassigned but it cannot be redeclared (within a given 'scope')
		* `let age = 72;`   
		to reassign, you could do math to the already existing variable 'age' as such: `age = age + 1`   
		this will allow 'age' to be reassigned: `age = 73` but it cannot be redeclared as such `let age = 76;` within the same scope 
	* Initializing w/ value is optional 
	* It does not create a property on global window object 

* Const (constant) is block scoped
	* It cannot be reassigned (not immutable, but variable reference cannot change) and cannot be redeclared (in the same scope) 
		* `const year = 1973;` cannot be reassigned or redeclared like 'let'. `year ++;` is invalid as well as `year = year +10;`
	* It must be initialized with value 
	* It does not create a property on the global window object 

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="methods" class="methods"></a>

### METHODS

Methods are functions that are properties of an object. There are 2 kinds: Instance Methods (built-in tasks) and Static Methods (tasks called directly on a object constructor)   

Adding a function as a property/value of an object 

* `alert()` pops up a message to the user in a pop-up window 
* `prompt()` can get input from the user 
	* `prompt(“what is your name?”);`  
	will send this question thru (with an answer box) in a pop-up window, allowing the user to answer. The answer will appear in the console 
* `console.log()` prints out whatever text is requested through the console (not on the page itself) 

<ins>KEYWORD “THIS” </ins>

A type of method (`this.`) added to objects in order to access/share pre-defined data. It's a common pattern to organize code: you take data, put it inside an object, then take associated functions and add them as methods to the same object and use the keyword THIS to access the data that was pre-defined 

[DOM Methods](#domMethods)

[String Methods](#stringMethods)

[Array Methods](#arrayMethods)

<ins>Math Object Methods</ins>

A built-in object that has properties and methods for mathematical constants and functions; it works with the Number type (*must be capital 'M')

`Math.random()` // returns any random decimal between 0-1 (not including 1)
`Math.floor(Math.random() * 10) + 1` // returns any random number between 1-10   
`Math.PI` // 3.14...   
`Math.floor(3.657)` // 3 (it will chop off any decimal digits, not round)   
`Math.round(3.657)` // 4 (it rounds to the nearest whole number)   
`Math.pow(7,2)` // 49 (raises the first digit to the power of the second digit)  
`Number(prompt());` will convert a string to a number (`<prompt>` always returns a string so in some cases you may want to convert it)   
`Math.sqrt` used with `%` modulo will help find odd/even numbers or sq roots   

To parse strings into numbers, you can use one of the following:

`parseInt` // returns integer
* if you have a string '21' but you need a number 21, you can put `parseInt('21')` // 21 is returned. You can use `parseInt('21') + 1` to get 22 (which you cannot do if '21' is a string)

`parseFloat` // returns 
* if you have a decimal you can use this method. for ex `parseFloat('33.5')` // 33.5 as a number value.

Note there must always be a number at the beginning of the `()` for example `parseInt('$99')` // NaN but `parseInt(99cents)` // 99 because it cannot start with a symbol or letter etc. only a number



###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="conditionals" class="conditionals"></a>

### CONDITIONALS

Making decisions with code *the most important element to learn to code 

<ins>Conditional statements:</ins> 

1. IF statements 
2. ELSE IF statements    
(must follow an IF statement; they function the same as an IF statement so it’s like a continuation of the IF statement) 
3. ELSE statements 

Conditionals are made in conjunction with Boolean logic and they work in order (from first code to last). Examples: 

> If you are younger than 18, you cannot enter the venue   
> If you are between 18 and 21 you can enter but cannot drink   
> Otherwise, you can enter and drink 

>`if(age < 18) {`   
 `console.log(“sorry, you are not old enough to enter the venue”)}`    
 `else if(age < 21) {`    
 `console.log(“you can enter, but cannot drink”)}`    
 `else { `   
 `console.log(“come on in and drink!”)}`

<ins>Switch Statements</ins>

This is an easier way to read and write some conditional statements

For example, if we had the following 'if' statements representing the days of the week...
`let day = 3`  
`if(day===1){`  
	`console.log("Monday")`  
`} else if(day===2){`  
	`console.log("Tuesday")`  
`} else if(day===3){`  
	`console.log("Wednesday")`  
`}` ...etc... 

you could use a 'switch statement' as such:  
`switch(day) {`  
	`case 1:`   
	`console.log("Monday")`  
	`break;`  
	`case 2:`  
	`console.log("Tuesday")`  
	`break;`  
	`case 3:`   
	`console.log("Wednesday")`  
	`break;`  
	...etc...  
	`default:`  
	`console.log("Invalid Day")`    
`}` 

* remember to add the `break;` or else the code will continue to run until the end of the entire switch statement
* the `default` statement is equivalent to the `else` statement that runs if all other cases are not true

<ins>Ternary Operator</ins>

a way to shorten if statements and condense code  
syntax: `condition ? expIfTrue : expIfFalse`  

Example:  
`let num = 7;`  
`if(num===7){`  
	`console.log('lucky');`  
`} else {`  
	`console.log('BAD!')`  
`}`  

could be written on one line using the terninary operator

`num === 7 ? console.log("lucky") : console.log("BAD!")`

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

	* Ex: printing numbers 1-5   
	`var count = 1;`   
	`while(count<6)`   
	`{console.log(“count is: “ + count); count++;}` 

	* ++ will add 1 to each number in succession 
	* +=2 will add 2 to each number in succession 

		* Ex: printing each character in a string   
	`var str = “hello”;`   
	`var count = 0;`   
	`while(count < str.length)`   
	`{console.log(str(count)); count++;}`   
		this will read as: “the string is defined as “hello” and the count starts at 0; while the count is less than the length of the string, add 1 to each count number for the letter of the string 

	* Infinite Loops: occur when the terminating condition in a loop is never False *you NEVER want this to happen! 

		* Example:  
		`var count = 0;`  
		`while (count < 10)`  
		`{console.log(count);`  
			this will read as: “count is = 0, while count is less than 10, console.log count.” But count is ALWAYS less than 10 since it isn’t being incremented, it will run an infinite loop 

	* `.indexOf()` returns the first index at which a given element can be found in the array, or –1 if not found. In WHILE LOOPS it allows you to expand the scope of the user answer  
		* Ex: adding an `.indexOf(“yes”)` to the annoy-o-matic will allow the user to answer “yes” or “yes we are” or “yes we have arrived” and because the `.indexOf(“yes”)` any answer that includes the word “yes”, even if it also includes more words than that, will complete the alert (and end the loop) 

2. FOR LOOPS: another way of repeating code; typical to use short/ one-letter variables like “i” instead of “count” 
the format always has 3 parts like this: for(initialize; condition; step) { … } 

	* For ex: printing numbers 1-5 

	* For Loop: below you can see the initialize value is var count = 0, the condition is count < 6,  and the step is count++. It is a more condensed version of the while loop below this example. NOTE: the variable is only declared within the loop 

		`for(var count = 0; count < 6; count++) {…}`

	* While Loop: this version is more drawn out and lengthy BUT as you can see the variable is not exclusive to the loop and must be declared outside of the loop  
		`var count = 1;`   
		`while(count < 6) {`  
		`console.log(“count is: “ + count);`  
		`count++; }`  

<ins>ITERATION</ins> (commonly seen in pages w comments): using loops and forEach to iterate over an array 

* Loop 
* ForEach: `arr.forEach(someFunciton)` 

	`var colors = [“red”, “orange”, “yellow”, “green”];`   
	`colors.forEach(function(color){`  
	`console.log(color);`  
	`});`  
	(note: ’color’ is a placeholder; can be named anything).  
  You are simply naming what each item in the array will be named and then calling each item in the console.log  
  Reads as "in the array 'colors' call each item 'color' and then console.log each color."

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="functions" class="functions"></a>

### FUNCTIONS

Allows us wrap bits of code into reusable packages. They are one of the building blocks of JS 

> `Function doSomething() {`    
  `console.log(“Hello World”); }`    

Then you call the function code: 

> `doSomething();`    

Note: you can refer to a function `doSomething` which will just give you back the original function code that was written (it will not run the code it will just reveal what code was written in the console. In order to run the code you have to have the parenthesis and semicolon like this: `doSomething();` 

* Ex: Twinkle Twinkle Little Star Song: instead of having to repeat the same code over and over again (writing many repeating console.logs which would not be DRY) every time you want the song sang you can write a function and then call the function whenever you want it sung: 

>`function singSong() {`   
  `console.log(“Twinkle, twinkle, little star,”);`   
  `console.log(“How I wonder what you are!”);`   
  `console.log(“Up above the world so high,”);`   
  `console.log(“Like a diamond in the sky.”);`   

>`singSong();`    
`singSong();`  

Calling the function `singSong();` twice (as above) will sing the song twice w/o rewriting each line 

Note: `clear()` is a function to clear the console 

* <ins>Return Keyword:</ins> add an input into a function and it will produce an output (INPUT > FUNCTION > OUTPUT)   
Without the return keyword you are getting a 'temporary’ response from the console.log. The information or code that is inputted is not being stored to be used elsewhere 

	`Function square(x) {`   
	`console.log(x * x); }`   

	`Square(4);    //16` 

	the response is only being console.logged; it is not able to be recalled again. In the console, the console.log will always return “undefined” unless a return has been specifically identified. 

	By using the return keyword you can in essence ‘save’ the information in the console to be recalled. You are able to ‘send’ information/code outside of a function and use it in other code within the console 

	`Function square(x) {`    
	`return x * x;`   

	`Square(4);     //16`    

	This response is being stored/saved within the console so it can be recalled in other code within the console, like within a string or other code. Without the return, a console.log alone cannot be recalled later in other code since it would be identified solely in the confines of the console.log function. So now I could write the following and the console would be able to recall the function above to use in the code: 

	`Var result = square(104);` 

	`Result     //10816` 

	In this case the function of square was recalled in the variable, the numbers computed (i.e. the square of 104), and stored in the variable called “result”; Result now stores the value of 10816 

	By using a return you are stopping/ ending the execution of a function. i.e. once the return keyword is executed the function will stop running. 

* Syntax to declare a function (there are 2) 

	1. Function Declaration: you have a function, the name of the function, pass in arguments, and pass in the body of the function within the {} brackets 

		`Function capitalize(str) {`   
		`return str.charAt(0).toUpperCase() + str.slice(1); } `

	2. Function Expression: set a variable which is set equal to a function; with this way, if you redeclare/ 

		`Var capitalize = function(str) {`    
		`return str.charAt(0).toUpperCase() + str.slice(1); } `  

<ins>NAMING FUNCTIONS</INS>   
It's best practice to use names that will easily read/translate into English (which makes it more developer/reader- friendly and easier to understand when revisited at a later date) 

* If you have `function sumArray(numbers)` (plural, since it relates to an array with mulitple elements) it makes sense to name the `.forEach` elements of that “number” (singular) as it relates to the individual element of the array numbers 

<ins>NAMESPACING</ins>
You can add a function with the same name if you identify each object of the function in a different way:   

>`function speak( ) {`    
  `return “WOOF!”; }` 

>`function speak( ) {`    
  `return “MEOW!”; } `

> `var dogSpace = { };`    
`var catSpace = { };`    

>`dogSpace.speak( ); `   
`catSpace.speak( ); `

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="arguments" class="arguments"></a>

### ARGUMENTS

Arguments are how to write functions that take inputs/ values; they are mutable and changing based on information provided. It's more than just repeating code because you can add new info/ change. A FB profile page has arguments that use the imputed data from the user.  
> 	`Function square(num) {`    
  	`console.log(num + num); }`   
	`square(10);    //100 `   
	`square(4);     //16 ` 

Functions can take multiple arguments at a time:   
(for a site that has to check credentials, you might add in multiple bits of info, like an email and password, which the code would have to check and then allow or deny access) 

>`function area(length, width) {`    
`console.log(length * width); }`    
`area(9,2);     //18`   


###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="arrays" class="arrays"></a>

### ARRAYS

an array is a way to group data in a list

* You can call each item in an array by calling the index   
`var something =[thing1, thing2, thing3...]`    
thing1 is at index 0, thing2 is at index 1, etc. 

* Empty arrays can be initialized in 2 ways  
`Var friends = [];`     //empty array  
`Var friends = new Array();` //empty array; uncommon way 

* Arrays can hold any type of data (numbers, stings, etc)   
`Var random_collection = [49, true, “Hermione”];` 

* Arrays have a length property  
`Var nums = [45, 37, 89,, 34];`  
`nums.length      //4` 
 
* Arrays can be modified (unlike strings)  
`let shoppingList = ['cheese', 'milk', 'ice cream']`  
`shoppingList[2] = 'ice cream'`
`shoppingList[shoppingList.length] = 'Tomatoes'` //adds to end of list
`shoppingList[0] = 'cheddar cheese'` // changes 'cheese' to 'cheddar cheese' at start of list

* Arrays are reference types. They're different than primitive datatypes. Prim Types are stored as actual values in a variable. Arrays variables reference to where that array is in memory  
`const myEggs = ['brown', 'brown']` could be changed to  
`myEggs.push('purple')` // `myEggs = ['brown', brown', 'purple']` but it could not be changed to  
`myEggs = ['blue', 'pink']` because this would be reassigning the variable not adding to the original reference

<a name="arrayMethods" class="arrayMethods"></a>
<ins>Array Methods</ins> are ways to modify arrays
1. PUSH( ): adds an item to the end of an array 
	`Var colors = [“red”, “orange”, “yellow”];`   
	`colors.push(“green”);`  
	// [“red”, “orange”, “yellow”, “green”] 

2. POP( ): removes an item from the end of an array 

	`Var colors = [“red”, “orange”, “yellow”];`    
	`colors.pop();` // [“red”, “orange”]  
	`pop();` // returns the removed element  
	`var col = colors.pop();` // orange 

3. UNSHIFT( ): adds an item to the start of an array 

	`Var colors = [“red”, “orange”, “yellow”];`   
	`colors.unshift(“infarared”)`  
	// [“infarared”, “red”, “orange”, “yellow”] 

4. SHIFT( ): removes an item from the start of an array 

	`Var colors = [“red”, “orange”, “yellow”];`  
	`colors.shift();` // [“orange”, “yellow”]  
	`Shift();` returns the removed element  
	`var col = colors.shift();` // orange 

5. `.includes` & `.indexOf`: will tell you if an array includes an item (it doesn't indicate where) or not. It will return T/F and it looks for direct matches. For ex, if you have an array  
`let ingredients = ['water', 'corn starch', 'flour']` then  
`ingredients.includes('fish')` // false
`ingredients.includes('shrimp')` // true
`ingredients.includes('corn')` // false (because it's looking for exact matches and doesn't look within a string)
`ingredients.includes('water', 3)` // false (because it is searching for 'water' after index 3, which doesn't exist)
`ingredients.indexOf('flour')` // 2 (it appears at index 2)  
if a value doesn't exist it will show `-1`

6. `.reverse` : will reverse the order of an array. Note that it reassigns the new value to the variable  
`let letters = ['T','C', 'E', 'P', 'S', 'E', 'R']`  
`letters.reverse = ['R', 'E', 'S', 'P', 'E', 'C', 'T']` // and now the variable 'letters' is reassigned to the new 'reversed' value

7. `.join` : will join items in an array into a single string  
`let letters = ['R', 'E', 'S', 'P', 'E', 'C', 'T']`
`letters.join(-) = ['R-E-S-P-E-C-T']` // joins them together w/ an '-' dash. Default it will put a comma between each item

8. `.slice` : has a similar function to the [string method](#stringMethods) 

9. `.splice` : has 3 different elements to either remove, add, or replace items of an array  
syntax: `array.splice(startIndex, deleteCount, ...items)` adding items to replace is optional  
<br> 
`let animals = ["shark", "salmon", "whale", "bear", "turtle"];`  <br>  
`animals.splice[1,0,"octopus"]` // reads: after index 1, delete nothing, and add "octopus"  
`let animals = ["shark", "octopus", "salmon", "whale", "bear", "turtle"];`  
<br>
`animals.splice[3,2] // ["whale", "bear"]` (when you delete items they will be returned in the spliced array in the console)  
`let animals = ["shark", "octopus", "salmon", "turtle"];` //your new array has deleted 2 items starting at index 3 and returned the new array

10. `.sort` : will sort an array based on the code unit values. the default for words is alphabetical HOWEVER it will not sort numbers in numerical order (it sorts them in based on their code values as strings)

<ins>Combining Arrays with Concat</ins>  

`.concat` will add arrays together  

`let fruits = ["apples", "bananas", "melons"]`  
`let veggies = ["broccoli", "carrots"]`  
`let meats = ["chicken", "steak", "beef"]`  

`console.log(fruits.concat(veggies));` //this will add the veggies array to the end of the fruits array  
`let allFood = fruits.concat(veggies, meats);` //this will put everything in on array and set it to the variable 'allFood'

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="objects" class="objects"></a>

### OBJECTS

Objects store data in key-value pairs; they have no order (it’s not a list like an array). Think: dictionary... you look something up based on a key to get a corresponding value 

>`Var person = { `   
  `name: “Travis”,`    
  `age: 21,`    
  `city: “LA” `   
`}; `   

* note the curly braces `{ }` are used instead of the square braces `[ ]` like in an array 

* Each element in stored under the key-value (in this case it’s ‘name’, ‘age’, ‘city’) 

* Objects can hold all sorts of data (strings, numbers, etc) just like arrays 

* To retrieve the data you can use bracket notation or dot notation 

	`Console.log(person[“name”]);` 
	`Console.log(person.name);` 

	* You cannot use dot notation if the property starts with a number   
		`someObject.1blah` //INVALID   
		`someObject[“1blah”]` //VALID 

	* You cannot use dot notation for property names with spaces   
		`someObject.fav color` //INVALID   
		`someObject[“fav color”]` //VALID 

	* You can lookup using a variable with bracket notation   
		`Var str = “name”`    
		`someObject.str` //DOESN’T EVALUATE OR LOOK FOR “NAME”   
		`someObject[str]` //EVALUATES STR AND LOOKS FOR “NAME” 

* Just like an array, access a property to reassign it or edit/change it    
	`person[“age”] += 1;`   
	`Person.city = “London”;`    
	`dog.age = 6;`     //this will add the key “age” to the object 

* Just like an array, there are a few methods of initializing objects 
	* Make an empty object and then add to it   
		`Var person = { }`    
		`person.name: “Travis”,`    
		`person.age: 21,`   
		`person.city: “LA”;`   

	* Add all the data at once (object literal notation, as seen in the initial ex for ‘objects’)   
		`Var person = {`    
		`name: “Travis”,`    
		`age: 21,`     
		`city: “LA” `   
		`}; `

	* Make a ‘newObject’  
		`Var person = new Object(); `  
		`person.name: “Travis”,`   
		`person.age: 21,`    
		`person.city: “LA”; `

###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="dom" class="dom"></a>

### DOM

Document Object Model is the interface between Javascript and HTML + CSS 

* <em>Select</em> an element and then <em>manipulate</em>
> Ex: select `h1` and then manipulate (change color from black to pink)    
`var h1 = document.querySelector(“h1”)`   
`h1.style.color = “pink”;` 

<ins>MANIPULATION</ins> 

1. Style: you can use the style property to manipulate an element's style 
	- Separation of Concerns: it's recommended for styles to be defined in a separate file(s). The style property allows for quick styling, for example for testing purposes 
	- There are 3 basic parts to a webpage: Structure, Behavior, Presentation. They overlap slightly in some areas but it is a generally accepted rule that each part is responsible for it's own contribution to the page (i.e. CSS is for styling, HTML is for stucture/ skeleton, Javascript is for function (VERB). 

		`var tag = document.getElementBy Id("highlight");`    
		`tag.style.color = "blue";`    
		`tag.style.border = "10px solid black";`    

2. Text & Content:  
	- textContent: returns a string of all the text contained in a given element   
	`<p>Hello <strong>World</strong></p> `   
	`var tag = document.querySelector("p");`    
	`tag.textContent `   
	//"Hello World"    
	*note it only returns the content, not the `<strong>` tag inside   

		`tag.textContent = "blahblahblah"`   
		//this will change the `<p>` to "blahblahblah" 

 	- Be careful overwriting with `.textContent` because it will change/ remove parts inside the content (i.e. in the above ex if you wrote "Goodbye World" it would also remove the `<strong>` tag) 

 	- **use `.innerHTML` as an alternative option to be able to select more specific tags. It will return everything as a string including the inside HTML elements 

	- You can write HTML (with tags etc) with .innerHTML and it will show on the page like normal HTML. However `.textContent` will not; it reads everything literally and does not read an `<h1>` tag (for ex) as an `<h1>`… 

3. Attributes: 

	`.getAttribute( );`   
	`.setAttribute( );` 

	`var link = document.querySelector("a");`    
	`link.getAttribute("href");`     //"www.google.com" 
	`link.setAttribute("href", www.dogs.com);`     
	//`<a href = www.dogs.com> I am a link</a>` 

	`Var img = document.querySelector("img");`    
	`img.setAttribute("src", "odie.png");`   
	//`<img src="odie.png");` 

	`Data- **` attributes: allow storage of extra info on  standard HTML elements w/o hacks of extra properties
	* `Data-key` is a data attribute that links a key to an identifier (i.e. a number) [see Drum Kit Project in #Javascript30 course]

<ins>EVENTS</ins> 

Events make things interactive (for ex clicking a button, hovering over a link, etc).  

* Process: first you select an element and then you add an event listener 

	"Listen for a click on this `<button>`"   
	"Listen for a hover event on the `<h1>`" 

`.addEventListener` is used very often and there are two parts: 

1. Type of event that you want to listen for 

2. The code you want to run when the event happens 

	Ex: display a message when a button has been clicked: 

	`<button>Click Me</button>`   
	`<p>No one has clicked me yet</p>` 

	`var button = document.querySelector("button");`    
	`var paragraph = document.querySelector("p");` 

SETUP CLICK LISTENER 

`button.addEventListener("click", function() {`    
`paragraph.textContent = "Someone clicked the button!"; });`   

You can have more than one 'listener' on an element 

<a name="domMethods" class="domMethods"></a>

<ins>DOM Methods</ins> are used to select elements
1. `document.getElementById( )` allows you to call an element using it’s ID tag   
	>`var tag = document.getElementById(“enter ID name here”);`   
	calling the variable ‘tag’ will bring up the entire item (whether it’s an `<li>` or other element) that contains the ID of the name entered 

2. `document.getElementsByClassName( )` allows you to call an element using it’s CLASS tag   
	>`var tags = document.getElementByClassName(“enter ClassName here”);`    calling the variable ‘tags’ will bring up the entire item (whether it’s an `<li>` or other element) that contains the CLASS NAME of the name entered
	* Note ‘tags’ (plural) because there are more than one 
	* You cannot use .forEach here because this is a list, not an array  

3. `document.getElementsByTagName( )` allows you to call any element with the same tag name   
	>`var tags = document.getElementsByTagName(“enter TagName here”);`   
	calling the variable ‘tags’ will bring up a list (even if there is only one element) of every element with the same tag name (like `<li>, <h1>`) 

4. `document.querySelector( )` returns the first element that matches a given CSS-style selector 
	> `var tag = document.querySelector(“#enter ID name here”);`    
	calling the variable ‘tag’ will bring up the first item (whether it’s an `<li>` or other element) that contains the ID of the name entered   
	`var tags = document.getElementByClassName(“.enter ClassName here”);`   
	calling the variable ‘tags’ will bring up the first item (whether it’s an `<li>` or other element) that contains the CLASS NAME of the name entered
	* Note that using `.querySelector` will give you an array 

5. `document.querySelectorAll( )` returns all the elements that match a given CSS-style selector   
	>`var tags = document.querySelectorAll(“h1”);`    
	calling the variable ‘tags’ will bring all the h1 elements   
	`var tags = document.querySelectorAll(“.enter ClassName here”);`   
	calling the variable ‘tags’ will bring all the h1 elements 
	* Note that using `.querySelectorAll` will give you an Node list

###### |[Table of Contents](#tableOfContents)| 


<hr>
<a name="numbers" class="numbers"></a>

##### Primitive Datatypes Continued...

### NUMBERS & NUMERIC OPERATIONS

The JS Console can be used like a calculator
* different operations are possible ( + - * / )
* Order of operations / (PEMDAS) Parenthesis, Exponents, Multiplication, Division, Addition, Subtraction 
* `+` is used to concatenate and `+=` is used to add (same w other operations)

<ins>Modulo</ins>: also called the remainder operator or Modulus is represented by `%`

* Ex: 10 % 3 will give you 1 
  (it will divide 10 into 3 and then just give you the remainder as the solution)
* 20 % 5 will give you 0 
  (because 20 goes into 5 evenly 4 times) 

* Used often to find odd/even numbers, etc 
  `if (x % 2 !=== 0)` would find ODD numbers (if a number modulus by 2 does not equal 0, you have an odd number. 
	* 42 % 2 is 42/2 which is 21 with no remainder (so modulo is 0) then the result is an even number.  
	* 21 % 2 is 21/2 which is 10 with a remainder of 1 (so modulo is not 0) you have an odd number. 

* Used in conjunction with the Math operator to find sq roots, etc (**Math must be capitalized in order to be recognized by the console) 
	* if (age % Math.sqrt(age) ===0) 
	   will produce only the sq roots of age 
	* 9 % Math.sqrt(9) === 0 
	  reads: “9 modulus the square root of 9, which is 3, results in no remainder then you have a perfect square (9/3 is 3, which means that if you divide a number by its own square root and you do not get a remainder, you have a perfect square)
 
###### |[Table of Contents](#tableOfContents)| 
###### |[Return to Primitive Datatypes](#pDatatypes)|

<hr>
<a name="strings" class="strings"></a>

##### Primitive Datatypes Continued...

### STRINGS

Strings are all/any content within quotation marks. They are used to represent and manipulate a sequence of characters. Learn more on [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

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
	
* Strings are immutable; you cannot manipulate/change specific characters (just 'call' upon them)
	* `let favSong = "Surfin' USA"` you cannot select the 'S' and change it to 'D' (for ex) as you can in other languages (`favSong[0] = "D"`) is invalid
	* you can remove characters `let gibberish = "abcdefg"` as such: `gibberish[gibberish.length -1]` will remove 'g'

<a name="stringMethods" class="stringMethods"></a>

<ins>String Methods</ins> are built in actions that can be perfomed on or with a particular string (such as: search w/in a string, replace parts, change case). You must add the `( )` for the method to work

* `.toUpperCase()` | `.toLowerCase()`    
`let msg = "you are grounded"` you can use `msg = msg.toUpperCase()` resulting in `msg = "YOU ARE SO GROUNDED"`

* `.trim()`   
`let color = "     purple"` you can use `color.trim();` resulting in `color="purple";`

Some methods accept arguments that modify their behavior. Arguments are passed inside of `( )`

* `.indexOf()` finds the index of an item in an array (it’s location in an array). Index starts at 0

	* `“hello”[0]` will produce: “h” (requests/calls for the character in the  0-position) 

 	* `“hello”[4]` will produce: “o” (requests/calls for the character in the 4-position) 

	* Inputting `“The Beatles”[4]` will produce: “B” 

* `slice()` accesses parts of a string (or array) using it's index
	* in an array you can use `slice()`   
	`Var fruits = [“banana”, “orange”, “lemon”, “apple”, “mango”];`    
	`var citrus = fruits.slice(1, 3);`    
	this will 'slice' the fruits array from index 1 and end the slice at index 3 resulting in `[“orange”, “lemon”]`   
	note: `var fruits = [“banana”, “orange”, “lemon”, “apple”, “mango”]` 

	* in a string you can use `slice()`   
	`"baseball".slice(4)` will start a slice at index[4] and continue to the end resulting in `"ball"`   
	`"superhero".slice[0,5]` will start a slice at index[0] and end the slice at index[5] resulting in `"super"`

* `.replace()`   
	* `'baseball is entertaining'.replace('entertaining', 'ok')` will result in `"baseball is ok"`


Here's the [MDN page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) listing possible string methods (on the left side)

<ins>String Template Literals</ins> allow embedded expressions which will be evaluated and turned into a resulting string

`I counted ${3+4} sheep;` // "I counted 7 sheep"

* use backticks (`) not single quotes with ${ }

`let animal = "pig"`    
`let sound = "oink"`   
`'${animal} says ${sound}'` (* these are backticks on each end not quotes)



###### |[Table of Contents](#tableOfContents)| 
###### |[Return to Primitive Datatypes](#pDatatypes)|

<hr>
<a name="boolean" class="boolean"></a>

##### Primitive Datatypes Continued...

### BOOLEAN
These statements can be used to combine the initial T/F statement to create more complex statements that also evaluate to T/F 
  

<ins>Comparison Operators</ins>   
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

  <ins>Double Equals v Triple Equals (== vs ===)</ins>

- == (double equal) performs type coercion
				- ex: var x = 5  //  x==”5” is TRUE   
				Here there is a number and a string. With the double equal JS will strip away the datatype and then compare the values to see if they are the same (it only cares that the core values are the same, not whether they are of the same datatype) 
				- General Rule: avoid using == as much as possible b/c there are odd exceptions
								- True == “1”  // true however this is only true in this case! (true == “12” // false) 
								- 0 == false  // true 
								- null == undefined // true 
								- NaN == NaN  // false 

- === (triple equal) no type coercion 
				- ex: var x = 5  //  x===”5” is FALSE   
				Here we have a number and a string. With the triple equal JS will keep and compare the datatype and the value and see if they are the same 
				- General Rule: always try to use === since it is more specific 

  <ins>Logical Operators</ins> (assuming below x = 5 and y = 9)

| Operator | Name | Example            | Result | Explanation                  |
|:--------:|:----:|--------------------|:------:|------------------------------|
|    &&    | AND  | x < 10 && x !== 5  | false  | requires both sides to be T  |
|   \|\|   |  OR  | y > 9 \|\| x === 5 |  true  | requires 1 side to be T      |
|    !     | NOT  | !(x===y)           |  true  | gives the opposite of result |

  <ins>Truthy / Falsy</ins> 

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
###### |[Return to Primitive Datatypes](#pDatatypes)|
<hr>
