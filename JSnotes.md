# JAVASCRIPT

* JS is the 'verb' of a webpage 
* JS is single threaded. This means that only one thing at a time is running and it finishes (in other words, at any given point in time JS is running at most one line of JS code)
* comment out using `//` (double slash)
* clear the console using the function `clear()`
* 'inspect' the page and use the console (developer's tool)
* docs are saved with ' .js ' 

ES6 is the most up-to-date version of Javascript. Find them throughout the notes with the title "ES6 (New JS Feature)"

The `debugger` can be used to track the console, step-by-step, in your code. It helps illuminate where you are at in the code, what you are telling the console, and how it is being read. 

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
- [Call Stack](#callStack)
- [HTTP Requests](#requests)

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

**Additional JS pages: How to link them (VS Code)**  
* If you want to separate your JS code and use two different documents for all the info, you can use separate documents that are linked via 'import' and 'export'  

Part I (in your documents)  
* in your HTML document, add a `type="module"` to the script tag:
```
<script src="docTitle.js" type="module"></script>
```  
* in your primary JS doc, add the following to the very top of the document  
```
import insertElementNameHere from './docTitle2.js';
```  
* in your secondary JS doc (saved to whatever title matching `./docTitle2.js`), add the following to the very bottom of the document
```
export default insertElementNameHere;
```
* See an example of this import/export with the Recipes Webpage

Part II (in VS Code Editor)
* Make sure you have the Live Server Extension on VS Code
* Have your HTML file open (saved as 'index.html')
* Open the folder with the documents you are using (This is on the left hand side menu bar). The doc's folder must be open in the sidebar
* on the HTML page, right click and select "Go Live" or CMD+L, CMD+O
* the page should open up in a new chrome window
* Part II Troubleshooting solution found [HERE](https://github.com/ritwickdey/vscode-live-server/issues/248)

###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="pDatatypes" class="pDatatypes"></a>

### PRIMITIVE DATATYPES

Different categories of data

* [NUMBERS](#numbers): whole number (4) fraction (9.3) negative (-10); All numbers are treated the same 

* [STRINGS](#strings): words or numbers inside quotations (single or double) like "Hello World" or "43"

* [BOOLEAN](#boolean): either TRUE or FALSE 

* NULL: variables that are explicitly *nothing*
	* used often in games for 'game over' or the end  
	```
	var currentPlayer = “charlie”;
		currentPlayer = null; 
		// game over
	```  
* UNDEFINED: variables that are declared but not initialized/ defined; it’s a ‘nothing’ value but only because it hasn’t been declared *yet*
	* `var name;`  OR `var age;`
	  both undefined; they are declared but no value is assigned (like `var name = “Helen”`) (in the console you'd get ‘undefined’ because they have no value assigned to them)  

NOTE: using `typeof` (not camelCase) will determine the datatype of whatever is put after it (note: the returned value is always a string)   

* `typeof 99` // "number"   
* `typeof mystery` // "string"  

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
General Rule: use **const** over **let**, use **let** over **var**, use **var** as little as possible (likely only with legacy code)

* Var (variable) are scoped to the ‘current execution context’ (a variable’s enclosing function or the global scope) 
	* A variable can be reassigned whenever and redeclared at any point 
	* Initializing with value is optional 
	* Global variables are added to window 
	* Scoped within functions

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

<ins>Scopes</ins>

1. Function Scope
	* the scope within a function
	* variables (var) are function scoped meaning that if they are declared within a given function they cannot be called outside of the function.
2. Block Scope 
	* The scope within a given block; 
	* 'let' and 'const' are both block scoped variables meaning they are available within the scope where they are declared (within the function, for ex, that they are declared) but not outside of that block
3. Lexical Scope
	* the scope of variables within different functions, nested functions, etc.
	* variables declared within a given function are available to other nested functions but not outside of the given function

<ins>ES6 (New JS Feature): **Destructuring**</ins>  
This is a short, clean syntax to 'unpack' values (from an array) or properties (from an object) into distinct variables

1. Destructuring Arrays
	```
	const raceResults = [
		'Eluid Kipchoge',
		'Feyisa Lelisa',
		'Galen Rupp',
		'Ghirmay Ghebreslassie',
		'Alphonce Simbu',
		'Jared Ward'
	]
	```
	Previously the only way to access parts of the array to assign it to a new value was to use it's index (as seen below:).  
	```
	const gold = raceResults[0];
	const silver = raceResults[1];
	const bronze = raceResults[2];
	```
	But now you can use this destructuring like this:
	```
	const [gold,silver,bronze] = raceResults
	```
	This will access the index of each part of the array and associate it to the same index of `raceResults`. In other words, `[gold]` is at index[0] so it will be connected to index[0] of `raceResults` which has the value of 'Eluid Kipchoge', and so on for index[1] and index[2].  

	You could also add 'spaces' to access different parts of the array as such (no idea whether they are actually from these countries!):
	```
	const [Kenyan, , Italian, German, , USA] = raceResults
	```
	By writing it in this way it will still apply each value according to it's index but will leave a 'blank' value where there is no value added. However note that it will assign the non-value to that index and move to the next index for the next value:
	```
	Kenyan  // 'Eluid Kipchoge'
	Italian // 'Galen Rupp'
	German  // 'Ghirmay Ghebreslassie'
	USA    //'Jared Ward'
	```
	You can also use `rest` to contain the elements into a new array:
	```
	const [winner, ...losers] = raceResults

	winner // 'Eluid Kipchoge'
	losers // ['Feyisa Lelisa', 'Galen Rupp', 'Ghirmay Ghebreslassie', 'Alphonce Simbu', 'Jared Ward']
	```

2. Destructuring Objects  
Similar to destructuring arrays however instead of destructuring based off the index position it is destructured based off the property name.
	```
	const runner = {
		first: "Eliud",
		last: "Kipchoge",
		country: "Kenya",
		title: "Elder of the Order of the Golden Heart of Kenya"
	}

	const {first, last} = runner

	first // "Eluid"
	last // "Kipchoge"
	```
	You can also save an existing property to a new name (with just one property or multiple properties):
	```
	const {country: nation} = runner
	const {country: nation, title: honorific}

	nation // "Kenya"
	honorific // "Elder of the Order of the Golden Heart of Kenya"
	```
	Or you can use the `rest` method to group parts of the object into a new array:
	```
	const {first, last, ...other} = runner

	other // [
		country: "Kenya",
		title: "Elder of the Order of the Golden Heart of Kenya"
	]
	```

3. Nested Destructuring  
You can use destructuring to access properties nested in objs/arrays  
	```
	const results = [{
		first: "Eliud",
		last: "Kipchoge",
		country: "Kenya"
	},
	{
		first: "Feyisa",
		last: "Lilesa",
		country: "Ethiopia"
	}]

	const [,{country}] = results
	// Ethiopia
	```
	This will access the second index of the array which is an object and it will access the object with the property name 'country'. Note the beginning comma which is written in as an empty reference to the first index of the array. 

	```
	const [{first: goldWinner}, {country}] = results

	goldWinner // "Eluid"
	country // "Ethiopia"
	```

	The above is renaming the property 'first' to 'goldWinner' and then accessing that property value. Then you also have the 2nd obj with property value of 'country' being accessed

4. Destructuring Parameters (this can be done with objects or arrays)    
	```
	const runner = {
			first: "Eliud",
			last: "Kipchoge",
			country: "Kenya",
			title: "Elder of the Order of the Golden Heart of Kenya"
		}
	```
	You can destructure the parameters themselves as well:
	```
	function print({first, last, title}) {
		console.log(`${first}, ${last}, ${title`})
	}

	print(runner)
	// Eliud, Kipchoge, Elder of the Order of the Golden Heart of Kenya
	```

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

A type of method (`this.`) added to objects in order to access/share pre-defined data. It is an object. It's a common pattern to organize code: you take data, put it inside an object, then take associated functions and add them as methods to the same object and use the keyword THIS to access the data that was pre-defined. See the [timerApp Project](https://cased27.github.io/timerApp/) for more examples.    

The value of `this` is different depending on where it is in the code. It may refer to the global window or it may be references inside a function causing it to have a different value.  

Note: If you use an `=>` (arrow function) it will refer the `this` to the global window or the parent function/window which can help allow you to access the desired scope and information.  

Below is a table to help determine the value of `this` in different scenarios  

| Question / Scenario                    | Value of `this`                                                                                                                                 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Was it an arrow function?              | `console.log(this)` on the first valid line above the arrow function. Value of `this` in the arrow function will be equal to that `console.log` |
| Was 'bind', 'call' or 'apply' invoked? | `this` is equal to the first argument of the 'bind', 'call' or 'apply'                                                                          |
| All other cases                        | `this` is equal to whatever is the to the left of the '.' in the method call                                                                    |


[DOM Methods](#domMethods)

[String Methods](#stringMethods)

[Array Methods](#arrayMethods)

<ins>Adding Methods to Objects</ins>  
You can add your own method to any object using the 'dot' notation  

```
const math = {
	numbers: [1, 2, 3, 4, 5],
	add: function(x,y) {
		return x+y
	},
	multiply: function(x,y) {
		return x*y
	}
}

math.add(5,6) // 11
math.multiply(6,7)  // 42
```

There is an updated newer/shorter syntax for the above that avoids having to do the 'key'-'value' syntax:

```
const math = {
	numbers: [1, 2, 3, 4, 5],
	add(x,y) {
		return x+y
	},
	multiply(x,y) {
		return x*y
	}
}
```

<ins>**Math** Object Methods</ins>

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

<ins>Map Method</ins>  
This method is used often to create a new array with the results of calling a callback on every element in the array

	* it will take an array and map them onto a new array 
	* the new array has to return a value; if nothing is returned it will not work

```
const numbers = [20, 21, 22, 23, 24, 25, 26, 27];

const doubles = numbers.map(function(num){
	return num * 2;
});

doubles

// [40, 42, 44, 46, 48, 50, 52, 54];
```
Note in the above example the 'return'. Without the 'return' it will not work (and show 'UNDEFINED')


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

```
if(age < 18) {
 console.log(“sorry, you are not old enough to enter the venue”)
} else if(age < 21) {
 console.log(“you can enter, but cannot drink”)
} else { 
 console.log(“come on in and drink!”)
}
```
<ins>Switch Statements</ins>

This is an easier way to read and write some conditional statements

For example, if we had the following 'if' statements representing the days of the week...  
```
let day = 3

if(day===1){
	console.log("Monday") 
} else if(day===2){
	console.log("Tuesday")
} else if(day===3){
	console.log("Wednesday")
} ...etc... 
```
you could use a 'switch statement' as such:  
```
switch(day) { 
	case 1:
	console.log("Monday")
	break;
	case 2:
	console.log("Tuesday")
	break;
	case 3:
	console.log("Wednesday")
	break;
	...etc...  
	default:
	console.log("Invalid Day")
}
```
* remember to add the `break;` or else the code will continue to run until the end of the entire switch statement
* the `default` statement is equivalent to the `else` statement that runs if all other cases are not true

<ins>Ternary Operator</ins>

a way to shorten if statements and condense code  
syntax: `condition ? expIfTrue : expIfFalse`  

Example:  
```
let num = 7;
if(num===7){
	console.log('lucky');
} else {
	console.log('BAD!')
}
```

could be written on one line using the terninary operator
```
num === 7 ? console.log("lucky") : console.log("BAD!")
```

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="loops" class="loops"></a>

### LOOPS

Loops are a way to condense code that is doing the same thing over and over again, i.e. rapidly complete repetitive tasks 
* Counter: is the starting point of a loop 
* Exit condition: criteria under which the loop stops (usually when it reaches a certain value) 
* Iterator: generally increments the ‘counter’ by a small amount on each successive loop until reaching the exit condition 

<ins>ITERATION</ins> (commonly seen in pages w comments): using loops and forEach to iterate over an array (*note that objects ARE NOT iterable)  

* ForEach: `arr.forEach(someFunction)` 
```
var colors = [“red”, “orange”, “yellow”, “green”];

colors.forEach(function(color){
	console.log(color);
});
```
(note: ’color’ is a placeholder; can be named anything).  
You are simply naming what each item in the array will be named and then calling each item in the console.log  
Reads as "in the array 'colors' call each item 'color' and then console.log each color."

DRY: Don’t Repeat Yourself; always keep your code as DRY as possible for time-saving and clean code 

<ins>ES6 (New JS Feature): **Spread**</ins>  
MDN: Spread syntax allows an iterable such as an array to be **expanded** in places where 0 + arguments (for func calls) or elements (for array literals) are expected. OR an object expression to be expanded in places where 0 + key-value pairs (for obj literals) are expected 
* Syntax: using the `...` (triple dots) in the argument

1. Spread for Function Calls  
This will expand an iterable (array, string, etc) into a list of arguments.  
If we had the following, we would get a value returned (in this case, the max)  
	```
	Math.max(3,4,5,6,7,12,19,99,3)
	// 99
	```
	However, if we had an array of numbers (for ex) and we tried to use that array as the argument, we would not get any returned value because it is not an acceptable type of argument. 

	```
	const nums = [9, 3, 2, 8];
	Math.max(nums); // NaN
	```
	This is where/why we can use 'spread' to result in:  

	```
	const nums = [9, 3, 2, 8];
	Math.max(...nums); // 9
	```

2. Spread in Array Literals  
This will create a new array using an existing array. It spreads the elements from one array into the new array
	```
	const odds = [1, 3, 5, 7, 9]
	const evens = [2, 4, 6, 8, 10]

	const allNums = [...odds, ...evens]

	allNums // [1, 3, 5, 7, 9, 2, 4, 6, 8, 10]
	```
	* Note that order matters (if you put `const evens` before `const odds` the order of the numbers would be switched)
	* This is a shorter syntax (and a bit easier to read/see) than using `.concat` (which acheives the same result)


3. Spread in Object Literals  
This will copy properties from one object into another object literal
	```
	const canine = {
		family: 'Caninae',
		furry: true
	};

	const dog = {
		...canine,
		isPet: true,
		adorable: true
	};

	// dog {
		family: 'Caninae'
		furry: true,
		isPet: true,
		adorable: true
	};
	```
	As you can see in the above ex, the object within `const canine` is added into the new object `const dog` using the spread method  
	* Note that spread behaves differently with obj literals and array literals. Also with nested arrays/objects

<ins>LOOPS</ins>

1. WHILE LOOPS: repeats code WHILE a condition is True. It's very similar to an IF statement except an IF statement will run the code one time, a WHILE LOOP will repeat a given code block while a condition remains True 

	* Ex: printing numbers 1-5   
	```
	var count = 1;
	while(count<6){
		console.log(“count is: “ + count); count++;
	}
	```
	* ++ will add 1 to each number in succession 
	* +=2 will add 2 to each number in succession 

		* Ex: printing each character in a string   
		```
		var str = “hello”;
		var count = 0;
		while(count < str.length){
			console.log(str(count)); count++;
		}
		```
		this will read as: “the string is defined as “hello” and the count starts at 0; while the count is less than the length of the string, add 1 to each count number for the letter of the string 

	* Infinite Loops: occur when the terminating condition in a loop is never False *you NEVER want this to happen! 

		* Example:  
		```
		var count = 0;
		while (count < 10){
			console.log(count);
		}
		```
		this will read as: “count is = 0, while count is less than 10, console.log count.” But count is ALWAYS less than 10 since it isn’t being incremented, it will run an infinite loop 

	* `.indexOf()` returns the first index at which a given element can be found in the array, or –1 if not found. In WHILE LOOPS it allows you to expand the scope of the user answer  
		* Ex: adding an `.indexOf(“yes”)` to the annoy-o-matic will allow the user to answer “yes” or “yes we are” or “yes we have arrived” and because the `.indexOf(“yes”)` any answer that includes the word “yes”, even if it also includes more words than that, will complete the alert (and end the loop) 

2. FOR LOOPS: another way of repeating code; typical to use short/ one-letter variables like “i” instead of “count” 
the format always has 3 parts like this: for(initialize; condition; step) { … } 

	* For ex: printing numbers 1-5 

	* For Loop: below you can see the initialize value is var count = 0, the condition is count < 6,  and the step is count++. It is a more condensed version of the while loop below this example. NOTE: the variable is only declared within the loop
		```
		for(var count = 0; count < 6; count++) {…}
		```
	* While Loop: this version is more drawn out and lengthy BUT as you can see the variable is not exclusive to the loop and must be declared outside of the loop

		```
		var count = 1   
		while(count < 6){   
			console.log(“count is: “ + count)  
			count++; 
		}
		``` 
3. FOR...OF is preferable for anything that is 'iterable' as a way to have more DRY code. It will iterate over the actual values any array without using the 'i' variable.

	Basic Syntax is:
	```
	for(variable of object) {
		statement
	}
	```
	Here is an example:
	```
	let subreddits = ['soccer', 'popheads', 'cringe', 'books'];
	```
	typically you would write a FOR LOOP as such using the variable `i`: 
	``` 
	for(let i=0; i < subreddits.length; i++){ 
		console.log(subreddits[i]);
	}
	```
	instead, you can write a FOR OF statement as such:  
	```
	for(let sub of subreddits){
		console.log(sub);
	}
	```
4. FOR...IN will loop over the keys, or properties, in an object
	Basic Syntax is:
	```
	for(variable in object) {
		statement
	}
	```
	Here is an example:
	```
	const jeopardyWinnings = {
		regularPlay : 2522700,
		watsonChallenge : 300000,
		tournamentOfChampions : 500000,
		battleOfTheDecades : 100000
	};
	```
	```
	for (let prop in jeopardyWinnings) {
		console.log(prop)
	};

	//regularPlay
	//watsonChallenge
	//... (all the keys in the object will be returned)
	```
	Note that if **FOR...OF** is used it will return an error
	```
	for (let prop of jeopardyWinnings) {
		console.log(prop)
	};

	//UNCAUGHT TYPE ERROR (because it isn't iterable with 'of')
	```
5. forEach is an array [method](#method) that will enable you to select individual elements within a function (works similarly to other loops; depends on what you need done in the code as to which one is preferred)
	* it accepts a callback function
	* it calls the function once per element in an array


6. loop over an OBJECT (*note the capital 'O' since this is a method). Typically you cannot loop through an object like you would an array. However you can use the following methods in order to loop through Objects (FOR...OF and FOR...IN)  

	`Object.keys(variable)` is a way to loop over an object and select the 'keys' inside the object  
	`Object.values(variable)` is a way to loop over an object and select the 'values' inside the object
	```
	let movieReviews = {
		'Finding Nemo' : 10,
		Shrek : 9,
		'Kill Bill' : 9.5,
		Alien : 8
	}
	```
	You could access the 'keys' and 'values' by using the above notation:

	```
	Object.keys(movieReviews)
	// selects keys like 'Finding Nemo', 'Shrek', etc. 
	```  
	
	```
	Object.values(movieReviews)
	// would select values like '10', '9', etc. 
	```

	Then you could use a FOR OF or FOR IN loop to loop through the Object and retrieve all the keys (movie titles):  
	```
	for(let movie of Object.keys(movieReviews)){
		console.log(movie);
	} 
	```
	You could also find the values associated with the movies using the following (resulting in the keys and their values, i.e. the movie titles and their ratings):  
	```
	for(let movie of Object.keys(movieReviews)){
		console.log(movie, movieReviews[movie]);
	}
	```

###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="functions" class="functions"></a>

### FUNCTIONS

Allows us wrap bits of code into reusable packages. They are one of the building blocks of JS 
```
Function doSomething() {    
	console.log(“Hello World”); }
```
Then you call & run the function code by doing this: 

``` 
doSomething(); 
```    

Note: you can refer to a function `doSomething` which will just give you back the original function code that was written (it will not run the code it will just reveal what code was written in the console. In order to run the code you have to have the parenthesis and semicolon like this: `doSomething();` 

* Ex: Twinkle Twinkle Little Star Song: instead of having to repeat the same code over and over again (writing many repeating console.logs which would not be DRY) every time you want the song sang you can write a function and then call the function whenever you want it sung: 
```
function singSong() {
	console.log(“Twinkle, twinkle, little star,”);
	console.log(“How I wonder what you are!”);
	console.log(“Up above the world so high,”);
	console.log(“Like a diamond in the sky.”);

singSong(); 
singSong();
```
Calling the function `singSong();` twice (as above) will sing the song twice w/o rewriting each line 

*Note: `clear()` is a function to clear the console 

* <ins>Return Keyword:</ins> add an input into a function and it will produce an output (INPUT > FUNCTION > OUTPUT)   
Without the return keyword you are getting a 'temporary’ response from the console.log. The information or code that is inputted is not being stored to be used elsewhere 
	```
	Function square(x) {
	console.log(x * x); }

	Square(4);    //16
	```
	the response is only being console.logged; it is not able to be recalled again. In the console, the console.log will always return “undefined” unless a return has been specifically identified. 

	By using the return keyword you can in essence ‘save’ the information in the console to be recalled. You are able to ‘send’ information/code outside of a function and use it in other code within the console 
	```
	Function square(x) {
	return x * x; 

	Square(4);     //16  
	```
	This response is being stored/saved within the console so it can be recalled in other code within the console, like within a string or other code. Without the return, a console.log alone cannot be recalled later in other code since it would be identified solely in the confines of the console.log function. So now I could write the following and the console would be able to recall the function above to use in the code: 
	```
	Var result = square(104);

	Result     //10816
	```
	In this case the function of square was recalled in the variable, the numbers computed (i.e. the square of 104), and stored in the variable called “result”; Result now stores the value of 10816 

	By using a return you are stopping/ ending the execution of a function. i.e. once the return keyword is executed the function will stop running. 

<a class="keywords" name="keywords"></a>

<ins>Async Keyword</ins>  

* Find out more in Colt's JS course Chapter 18
* async functions always return a Promise
* If the function returns a value, the Promise will be resolved with that value
* if the function throws an exception, the Promis will be rejected
* note that requests can be parallel or sequential (which will effect the timing in which they are executed. Sometimes it will not be notable as far as something showing up, but behind the scenes they are happening at very different times)

<ins>Await Keyword</ins>  

* Find out more in Colt's JS course Chapter 18
* the await keyword can only be used *inside* an async function
* await will pause the execution of the function, waiting for a promise to be resolved

<ins>Functions as Return Values</ins>

```
function multiplyBy(num) {
	return function(x){
		return x * num;
	}
}

const triple = multiplyBy(3);
triple(6)  // 18
triple(5)  // 15
```

Here you have a function set as a return value. By setting the function multiply() to a variable you can then call the variable and add a parameter. Above you are setting 'num' to 3 (in the 'const triple') and then calling that function to run the inner function (setting x to 6) and then running through the function

* Syntax to declare a function (there are 2) 

	1. Function Declaration: you have a function, the name of the function, pass in arguments, and pass in the body of the function within the {} brackets 
		```
		Function capitalize(str) {
			return str.charAt(0).toUpperCase() + str.slice(1); }
		```
	2. Function Expression: set a variable which is set equal to a function; with this way, if you redeclare/ 
		```
		Var capitalize = function(str) {  
			return str.charAt(0).toUpperCase() + str.slice(1); } 
		```
<ins>NAMING FUNCTIONS</INS>   
It's best practice to use names that will easily read/translate into English (which makes it more developer/reader- friendly and easier to understand when revisited at a later date) 

* If you have `function sumArray(numbers)` (plural, since it relates to an array with mulitple elements) it makes sense to name the `.forEach` elements of that “number” (singular) as it relates to the individual element of the array numbers 

<ins>NAMESPACING</ins>
You can add a function with the same name if you identify each object of the function in a different way:   

```
function speak( ) {
	return “WOOF!”; }

function speak( ) {
	return “MEOW!”; }


var dogSpace = { };
var catSpace = { }; 

dogSpace.speak( );
catSpace.speak( );
```

<ins>Function Expressions</ins>
This is another way to write a function where you assign a function to a variable

```
const sum = function(x, y) {
	return x + y;
}

sum(4, 6)
// 10
```

you can also do this while naming the function (which may, in some cases, be useful)

```
const product = function multiply(x, y) {
	return x * y;
}

product(3, 5);
// 15
```

note that you cannot call the function mulitply() since the console cannot identify it as such. but there may be cases in which naming the function is useful and it's good to know you can do it

<ins>Arrow Functions</ins>  
The arrow function is a way to condense function codes. See below for the difference in syntax between a regular function and an arrow function

Regular Function Syntax:
```
const square = function(x){
	return x*x
}
```
Arrow Function Syntax:
```
const square = (x) => {
	return x*x
}
```
Note that the parenthesis are optional in an arrow func when there is only one parameter (i.e. 'x' can be with or without parenthesis however if the parameter was (x,y) the parenthesis would be required)

Sometimes there is an *implicit return* when using the arrow function. For example:  
Normal Arrow Function:
```
const square = n => {
	return n*n
}
```
Implicit Return Arrow Function:  
```
const square = n => (
	n*n
)
```
Sometimes it can be expressed on one line:
```
const square = n => (n*n);
```

Note that the implicit return uses parenthesis instead of curly braces. And there is no return specified (JS will give you the 'squiggly red' error underline to notify you that it is not correct syntax in the implicit return statements)

<ins>Functions are Objects!</ins>

**Adding objects to functions is how you create a method!**

```
function add(x, y){
	return x + y;
}
function subtract(x, y){
	return x - y;
}
function multiply(x, y){
	return x * y;
}
function divide(x, y){
	return x / y;
}

const operations = [add, subtract, multiply, divide];

operations[1](100, 4)
// 96
```

here you are calling index 1 of the const 'operations' (which is 'subtract) and then providing parameters for the function and executing it with those parameters

```
using the same ex above...

const thing = {
	doSomething: multiply
}
thing.doSomething(50,2)

// 100
```

Here you have an object calling an object and executing a function. This is how you create a method!

<ins>Functions as Arguments</ins>

```
function callThreeTimes (f) {
	f();
	f();
	f();
}

function cry(){
	console.log(boo hoo);
}

callThreeTimes(cry)

//boo hoo
//boo hoo
//boo hoo
```
Here you have a function being run through another function as an argument

<ins>Callback Functions</ins>

Anytime you pass a function within another function it is considered a 'callback function'. It's very common in JS. You can write your own callback function or many methods that are used are callback functions

```
function grumpy(){
	alert("UGH GO AWAY")
}

setTimeout(grumpy, 5000)
```
// after 5000 ms you will get the alert in the function grumpy()

```
setTimeout(function (){
	alert("HELLO")
}, 5000)

```
This is another way to write the same thing as before (/above) but just adding the function directly within the setTimeout()

<ins>Hoisting</ins>

Hoisting concerns the order in which JS runs code. It behaves differently depending on whether you use VAR, LET, or CONST (and is one of the purposes of LET and CONST to avoid these errors/issues)

```
console.log(animal);
var animal = 'Cat'

// undefined
```
Why 'undefined' and not 'UNCAUGHT type ERROR"? This is because JS is identifying the variable 'animal' as undefined first, then console.logging it, then assigning the variable's value to 'cat'. aka it's 'hoisting' the variable

```
console.log(animal);
let animal = 'Cat'

// UNCAUGHT TypeERROR"
```
LET is not hoisted like VAR so if you try to console.log it *before* you declare it, it will not work

```
howl()

function howl(){
	console.log(AWOOOO);
}

// AWOOOO
```
functions *are* hoisted; so you can call a function before you define that function and it will still run the same. However, if you assign the function to a variable it will work in the same way as the variables did above

<ins>ES6 (New JS Feature): **Default Parameters**</ins>  
This is a new feature of JS in which you can write in the default parameter/ argument in a function (instead of adding a bunch of code as the default if/when someone doesn't add in 2 parameters/arguments)

```
function mulitply(a, b = 1) {
	return a*b;
}

multiply(4)  // 4
multiply(4,5) // 20
```  
In the above example, the default parameter/argument for 'b' is set to 1 directly inside the argument of the function. If no value is set for 'b', it will run the default value of 1 and run the code. If a value is set it will run the code as normal without the default value.  
* Note that the default parameter/argument is always the second value; this will not work the same if 'a' is set to a default  
* The default value doesn't have to only be a number; it can be a string, an array, etc.
* You can add more than one default as well. (but remember JS will always read the code in relation to its defined parameters)
```
function multiply(a, b=1, c=' Good Job!') {
	return a*b + c;
}
multiply(5) // "5 Good Job!"
```

<ins>ES6 (New JS Feature): **REST**</ins>  
* Despite looking similar to 'Spread', it is different  
* It allows you to add as many agruments as you'd like in your function. (There is an 'old way' to do this as well but the new way is better)
* It collects all remaining arguments into an actual array (which is what the 'old way': the 'arguments object' did not do which resulted in a lot of shortcomings)

```
function someNums(...nums){
	console.log(nums);
}

someNums(4,5,6,7)
// [4,5,6,7]
```
In the above ex, the argument in `someNums` (4,5,6,7) is added into a new array creating `[4,5,6,7]`

You can also use it when you have additional/remaining arguments. If you want to have an array with names (including first, last, and any additional names/titles) you could use this method to add in those misc remaining titles:  
```
function fullName(first, last, ...titles){
	console.log('first', first)
	console.log('last', last)
	console.log('titles', titles)
}

fullName('Tom', 'Jones', 'III', 'Jr.');
// first Tom
	last Jones
	titles ['III', 'Jr.']
```
As you can see, the extra/unclaimed 'titles' are added to an array at the end.   

Order matters (the `rest` paramenter MUST BE the last parameter). There also cannot be other parameters *after* the `rest` method (for obvious reasons, if `rest` accumulates the rest of the remaining parameters it would not know what to do with extra parameters after that)  
```
function fullName(...titles, first, last) // INVALID
function fullName(first, last, ...titles, ...misc)  // INVALID
```

<ins>JS Classes - Syntactical Sugar</ins>  

```
class Color {
	constructor(r, g, b) {
	}
}
```
Above is just the basic structure of a JS class; It must have a `class` keyword as well as call the `constructor` and then you would add in whatever code you wanted to run. This is used with the `new` keyword as well (Colt's JS course Section 19)

* Another few important keywords are the following:

	* Extends: this is used to extend a function into another one.  
	```
	class Pet {
		constructor(name, age){
			this.name = name;
			this.age = age;
		}
		eat(){
			return `$(this.name) is eating!`;
		}
	}
	class Cat extends Pet {
		meow(){
			return 'MEOW!';
		}
	}
	class Dog extends Pet {
		bark() {
			return 'Woof!'
		}
	}

	```
	* Super: is another way to refer to a 'parent' function


###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="arguments" class="arguments"></a>

### ARGUMENTS

Arguments are how to write functions that take inputs/ values; they are mutable and changing based on information provided. It's more than just repeating code because you can add new info/ change. A FB profile page has arguments that use the imputed data from the user.  
```
Function square(num) {
	console.log(num + num); }

square(10);    //100 
square(4);     //16
```
Functions can take multiple arguments at a time:   
(for a site that has to check credentials, you might add in multiple bits of info, like an email and password, which the code would have to check and then allow or deny access) 
```
function area(length, width) {
	console.log(length * width); } 
	
	area(9,2);     //18
```

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
	```
	let shoppingList = ['cheese', 'milk', 'ice cream'];

	shoppingList[2] = 'ice cream'

	shoppingList[shoppingList.length] = 'Tomatoes'` 
	//adds to end of list

	shoppingList[0] = 'cheddar cheese'` 
	// changes 'cheese' to 'cheddar cheese' at start of list
	```

* Arrays are reference types. They're different than primitive datatypes. Prim Types are stored as actual values in a variable. Arrays variables reference to where that array is in memory  
	```
	const myEggs = ['brown', 'brown'] 
	```
	could be changed to:
	```  
	myEggs.push('purple')` 
	// `myEggs = ['brown', brown', 'purple']
	``` 
	but it could not be changed to:
	``` 
	myEggs = ['blue', 'pink']
	``` 
	because this would be reassigning the variable not adding to the original reference

<a name="arrayMethods" class="arrayMethods"></a>
<ins>Array Methods</ins> are ways to modify arrays
1. PUSH( ): adds an item to the end of an array 
	```
	Var colors = [“red”, “orange”, “yellow”];

	colors.push(“green”);
	// [“red”, “orange”, “yellow”, “green”] 
	```
2. POP( ): removes an item from the end of an array 
	```
	Var colors = [“red”, “orange”, “yellow”];

	colors.pop();
	// [“red”, “orange”]

	pop();
	// returns the removed element

	var col = colors.pop();
	// orange 
	```
3. UNSHIFT( ): adds an item to the start of an array 
	```
	Var colors = [“red”, “orange”, “yellow”]; 

	colors.unshift(“infarared”)
	// [“infarared”, “red”, “orange”, “yellow”] 
	```
4. SHIFT( ): removes an item from the start of an array 
	```
	Var colors = [“red”, “orange”, “yellow”];

	colors.shift();
	// [“orange”, “yellow”]

	Shift();
	returns the removed element 

	var col = colors.shift();
	// orange 
	```
5. `.includes` & `.indexOf`: will tell you if an array includes an item (it doesn't indicate where) or not. It will return T/F and it looks for direct matches. For ex, if you have an array  
	```
	let ingredients = ['water', 'corn starch', 'flour', 'shrimp']
	```
	then:
	```  
	ingredients.includes('fish') // false
	ingredients.includes('shrimp') // true
	ingredients.includes('corn') // false 
	``` 
	(because it's looking for exact matches and doesn't look within a string)
	```
	ingredients.includes('water', 3) // false 
	```
	(because it is searching for 'water' after index 3, which doesn't exist)
	```
	ingredients.indexOf('flour') // 2 
	```
	(it appears at index 2)  
	*Note: if a value doesn't exist it will show `-1`

6. `.reverse` : will reverse the order of an array. Note that it reassigns the new value to the variable  
	```
	let letters = ['T','C', 'E', 'P', 'S', 'E', 'R']
	letters.reverse = ['R', 'E', 'S', 'P', 'E', 'C', 'T'] 
	```
	*Note: now the variable 'letters' is reassigned to the new 'reversed' value

7. `.join` : will join items in an array into a single string  
	```
	let letters = ['R', 'E', 'S', 'P', 'E', 'C', 'T']
	letters.join(-) = ['R-E-S-P-E-C-T']  OR
	letter.join() = [RESPECT]
	```
	joins them together w/ a '-' dash or nothing. Default it will put a comma between each item

8. `.slice` : has a similar function to the [string method](#stringMethods) 

9. `.splice` : has 3 different elements to either remove, add, or replace items of an array  
syntax: `array.splice(startIndex, deleteCount, ...items)` adding items to replace is optional  
```
let animals = ["shark", "salmon", "whale", "bear", "turtle"];

animals.splice[1,0,"octopus"] 
// reads: after index 1, delete nothing, and add "octopus"

let animals = ["shark", "octopus", "salmon", "whale", "bear", "turtle"];
```
when you delete items they will be returned in the spliced array in the console: 
```
animals.splice[3,2] 
// ["whale", "bear"]

let animals = ["shark", "octopus", "salmon", "turtle"]; 
//your new array has deleted 2 items starting at index 3 and returned the new array
```
10. `.sort` : will sort an array based on the code unit values. 
* Default: `.sort` will convert everything to a string.
* Words will be sorted alphabetically (by default) HOWEVER it will not sort numbers in numerical order (since they are treated as strings they are sorted based on their string code value (see MDN on number values as strings))

	The general syntax is as follows:
	```
	arr.sort(compareFunc(a,b))
	```
	* If `compareFunc(a,b)` returns less than 0 (i.e. negative), sort A before B
	* If `compareFunc(a,b)` returns 0, leave A and B unchanged with respect to each other
	* If `compareFunc(a,b)` returns greater than 0 (i.e. positive), sort B before A

	```
	const prices = [400.50, 3000, 99.99, 35.99, 12.00, 9500];

	const badSort = prices.sort();
	const assendSort = prices.sort((a,b) => a-b);

	badSort // [12, 3000, 35.99, 400.5, 9500, 99.99]
	assendSort // [12, 35.99, 99.99, 400.5, 3000, 9500]
	```
	`badSort` is the default result of using the sort() method with numbers. The numbers are not evaluated numerically (as noted aboeve) but instead converted into strings and compared based on their string values. This doesn't result in any meaningful ordering.

	In order to compare the numbers numerically, you have to do something like what you see in `assendSort`  

	`assendSort` goes through each element in the array and compares them. So it will take '400,5' and subtract it with '3000'. This returns a negative number so it will sort a (in this case '400.5') before b ('3000'). It will take 35.99 (as 'a') and subtract it with 12 (as 'b') and get a positive number. So it will sort 'b' (12) before 'a' (35.99). If the values are equal they will remain the same (the order would not change)

	you could do the following to get a decending order:

	```
	const decendSort = prices.sort((a,b) => b-a);
	```

11. `.find` : returns the value of the first element in the array that satisfies the provided testing function. Basically, it's a simple search/find method to look for a specific value and it will stop upon the first match to that value
	```
	let movies = [
		"The Fantastic Mr. Fox",
		"Mr. and Mrs. Smith",
		"Mrs. Doubtfire",
		"Mr. Deeds"
	]
	const movie = movies.find(movie => {
		return movie.inclueds('Mrs.');
	})

	movie // "Mr. and Mrs. Smith"
	```
	* Note that this method is case sensitive 
	* It will search through the array for the first match to the value "Mrs." and will stop on the second item (index[1])

12. `.filter` : creates a new array with all elements that pass the test implemented by the provided function
```
const nums = [34, 35, 67, 54, 109, 102, 32, 9]

const odds = nums.filter(n => n % 2 === 1);
const evens = nums.filter(n => n % 2 === 0);

odds // [35, 67,109, 9]
evens // [34, 54, 102, 32]
```

13. `.every` & `.some` : these are boolean methods (return either TRUE or FALSE)
	* `.every` tests whether all elements in the array pass the provided function

	```
	const words = ["dogs", "dig", "log", "bag", "way"]

	const allWords = words.every(word => word.length === 3)

	allWords // true;
	```
	this will return 'true' only if ALL the values match the test (in this case all the values have a word length of 3 so it is true)

	* `.some` tests whether any elements in the array pass the provided function
	```
	const words = ["dog", "jello", "log", "cupcake", "bag", "wag"]

	const anyWords = words.some(word => word.length > 4);

	anyWords // true;
	```
	this will return 'true' if ANY (i.e. some) of the values match the test (in this case there are various words with a length less than 4 so it is true)

14. `.reduce` executes a reducer function on each element of the array resulting in a single value (for example, summing, finding a max value, tallying data or results)  

	<ins>Finding the SUM or PRODUCT using `.reduce()`
	```
	[3, 5, 7, 9, 11].reduce((accumulator, currentValue) => {
		return accumulator + currentValue;
	})
	```

	the reduce() method above will go through each value of the array, store the accumulated value, and then use that accumulated value to continue through the array. If there is no initial value the first value of the array will be used as the first value/ accumulator. It looks like this (using the above as the example):

| Callback    | Accumulator | currentValue | Return Value |
|-------------|:-----------:|:------------:|:------------:|
| First call  |      3      |      5       |      8       |
| Second call |      8      |      7       |      15      |
| Thrid call  |     15      |      9       |      24      |
| Fourth call |     24      |      11      |      35      |

	If you wanted to get the product of the values (instead of the sum, as seen above) you could write the code like this:
	```
	[3, 5, 7, 9, 11].reduce((accumulator, currentValue) => {
		return accumulator * currentValue;
	})
	```
	<ins>Finding a MAX VALUE using `reduce()`</ins>
	```
	const grades = [87, 64, 96, 92, 88, 99, 73, 70, 64]

	const maxGrade = grades.reduce((max, currVal) => {
		if(currVal > max) return currVal;
		return max;
	})
	```
	Running through the array would look like this where you have each value being compared to each other and the higher value is returned and compared to the next value in the array

| Callback    | Accumulator | currentValue | Return Value |
|-------------|:-----------:|:------------:|:------------:|
| First call  |     87      |      64      |      87      |
| Second call |     87      |      96      |      96      |
| Thrid call  |     96      |      92      |      96      |

	This will continue through the entire array until it discovers that '99' is the max value

	<ins>TALLYING using `.reduce()`</ins>  
	Using reduce in this way will use an object

	```
	const votes = ['y', 'y', 'n', 'y', 'n','y','n','y','n','n','n','y','y',]

	const tallyVotes = votes.reduce((tally, currentVote) => {
		tally[currentVote] = (tally[currentVote] || 0) + 1;
		return tally;
	}, {});

	//Note that the {} empty curly braces at the end is the initial value

	tally // {y: 7, n:6}
	```
	the above reads: the constant 'tallyVotes' will take two parameters 'tally' and 'currentVote' and run them through the code. If tally of currentVote does not exist (i.e. the first time the code is run through the value is set to an empty object) it will set the values to their current values OR set them to 0 and then it will add one. So when you run through the first time you get your first 'y' and it will be set to the current value OR 0 (which are both 0 anyway) and then add one resulting in {y:1}. The next round through there is another 'y'. So you have y[1] = y[1] or 0, which is one, then you add 1, resulting in {y: 2}


<ins>Combining Arrays with Concat</ins>  

`.concat` will add arrays together  
```
let fruits = ["apples", "bananas", "melons"]
let veggies = ["broccoli", "carrots"]
let meats = ["chicken", "steak", "beef"]

console.log(fruits.concat(veggies));
//this will add the veggies array to the end of the fruits array  
let allFood = fruits.concat(veggies, meats);
//this will put everything in on array and set it to the variable 'allFood'
```
###### |[Table of Contents](#tableOfContents)| 
<hr>
<a name="objects" class="objects"></a>

### OBJECTS

Objects store data in key-value pairs; they have no order (it’s not a list like an array). Think: dictionary... you look something up based on a key (a word) to get a corresponding value (a definition)
```
Var person = { 
  name: “Travis”,
  age: 21,
  city: “LA” 
}; 
```
* note the curly braces `{ }` are used instead of the square braces `[ ]` like in an array 

* like arrays, objects hold references to their values; so when talking about equality they are not always equal even when it may appear so.   
`{a}` === `{a}` // false because each object created has a different reference point in JS that it is stored to. the value itself (`a` in this case) is not evaluated and therefore each object with a diff reference value are not equal

* Each element in stored under the key-value (in this case they keys are ‘name’, ‘age’, ‘city’ and the value is the corresponding info). Note that these keys/ properties, are automatically converted into strings

* Objects can hold all sorts of data (strings, numbers, etc) just like arrays 

* To retrieve the data you can use bracket notation or dot notation 
	```
	Console.log(person[“name”]);
	Console.log(person.name);
	```
	* You cannot use dot notation if the property starts with a number   
		```
		someObject.1blah //INVALID   
		someObject[“1blah”] //VALID 
		```
	* You cannot use dot notation for property names with spaces   
		```
		someObject.fav color //INVALID   
		someObject[“fav color”] //VALID 
		```
	* You can lookup using a variable with bracket notation   
		```
		Var str = “name”    
		someObject.str //DOESN’T EVALUATE OR LOOK FOR “NAME”   
		someObject[str] //EVALUATES STR AND LOOKS FOR “NAME” 
		```
* Just like an array, access a property to edit/change it   
	```
	person[“age”] += 1;   
	Person.city = “London”;    
	dog.age = 6;     
	//this will add the key “age” to the object 
	```
* Just like an array, there are a few methods of initializing objects 
	* Make an empty object and then add to it   
		```
		Var person = { }    
			person.name: “Travis”,    
			person.age: 21,   
			person.city: “LA”;   
		```
	* Add all the data at once (object literal notation, as seen in the initial ex for ‘objects’)   
		```
		Var person = {    
			name: “Travis”,    
			age: 21,     
			city: “LA”    
		}; 
		```
	* Make a ‘newObject’ (less common)  
		```
		Var person = new Object();   
			person.name: “Travis”,   
			person.age: 21,    
			person.city: “LA”; 
		```

###### |[Table of Contents](#tableOfContents)| 

<hr>
<a name="dom" class="dom"></a>

### DOM

**Document Object Model** is the interface between Javascript & HTML + CSS 

* *Select* an element and then *manipulate*  
Ex: select `h1` and then manipulate (change color from black to pink)
```   
var h1 = document.querySelector(“h1”)   
h1.style.color = “pink”; 
```

<a name="domMethods" class="domMethods"></a>

<ins>DOM Methods</ins> are used to select elements. I've separated these very useful list of DOM methods into sections: (A) [Selecting Elements](#selectingElements) (B) [Manipulation](#manipulation) (C) [Changing/ Removing/ Adding Elements](#changingElements).  

<a name="selectingElements" class="selectingElements"></a>
A. <ins>SELECTING ELEMENTS</ins>  

`document.getElementById( )` allows you to call an element using it’s ID tag
```
var tag = document.getElementById(“jfkIdName”);
```
calling the variable ‘tag’ will bring up the entire item (whether it’s an `<li>` or other element) that contains the ID of the name entered 

`document.getElementsByClassName( )` allows you to call an element using it’s CLASS tag   
```
var tags = document.getElementByClassName(“xyzClassName”);
```
calling the variable ‘tags’ will bring up the entire item (whether it’s an `<li>` or other element) that contains the CLASS NAME of the name entered
* Note ‘tags’ (plural) because there are more than one 
* You cannot use .forEach here because this is a list, not an array  

`document.getElementsByTagName( )` allows you to call any element with the same tag name   
```
var tags = document.getElementsByTagName(“abcTagName”);
```   
calling the variable ‘tags’ will bring up a list (even if there is only one element) of every element with the same tag name (like `<li>, <h1>`) 

`document.querySelector( )` returns the *first* element that matches a node (or CSS-style selector). Note it only selects a single element
```
var tag = document.querySelector(“#jfkIdName”);
```    
calling the variable ‘tag’ will bring up the first item (whether it’s an `<li>` or other element) that contains the ID of the name entered
```
var tags = document.getElementByClassName(“.xyzClassName”);
```
calling the variable ‘tags’ will bring up the first item (whether it’s an `<li>` or other element) that contains the CLASS NAME of the name entered
* Note that using `.querySelector` will result in an HTML element 

`document.querySelectorAll( )` returns a *collection* (or node list) containing all matching element nodes (using CSS-style selectors)    
```
var tags = document.querySelectorAll(“h1”);
```    
calling the variable ‘tags’ will bring all the h1 elements
```  
var tags = document.querySelectorAll(“.abcClassName”);
```   
calling the variable ‘tags’ will bring all the h1 elements 
* Note that using `.querySelectorAll` will give you an Node list unlike the other methods which return HTML Collections
<br>

<a name="manipulation" class="manipulation"></a>
B. <ins>MANIPULATION</ins> 

1. Style: you can use the style property to manipulate an element's style 
	* Separation of Concerns: it's recommended for styles to be defined in a separate file(s). The style property allows for quick styling, for example for testing purposes 
	* There are 3 basic parts to a webpage: **Structure, Behavior, Presentation**. They overlap slightly in some areas but it is a generally accepted rule that each part is responsible for it's own contribution to the page (i.e. CSS is for styling, HTML is for stucture/ skeleton, Javascript is for function (VERB). 
		```
		var tag = document.getElementBy Id("highlight");    
		tag.style.color = "blue";    
		tag.style.border = "10px solid black";    
		```
	`.getComputedStyle` is a method that can return an object containing the CSS style components and properties of an element (that can come from JS or the CSS style sheet, etc)
	* you can retrieve the style information and/or change it 
	* it is a great way to understand what is happening on the page as far as style goes

	`.classList` will allow us to access the classes and do something with it
	* `classList.remove` will remove any specified class  
	* `classList.add` will add any specified class  
	* `classList.toggle` will toggle (appear and disappear / add and remove) a class. (i.e. if it has the class, remove it. If it doesn't have the class, add it)  

2. Text & Content:  
You can access text or content and/or change that text through the DOM

* `.textContent`: returns a string of ALL text contained in a given element. It will maintain the formatting (spacing, etc) but not specific tags within.

* `.innerText`: will select all the text inside of the selected element (just like `textContent`) but will not maintain formatting (like spacing) and will remove tags, etc (just the text)

	```   
	<p>Hello <strong>World</strong></p>
	var tag = document.querySelector("p");

	tag.textContent    
	//"Hello World" 

	tag.innerText
	//"Hello World"
	```   
	note it only returns the content, not the `<strong>` tag inside (it will change/ remove parts inside the content) 

	The below example shows the main difference between the two. If we had the following `<p>` element  

	```
	<p id="special"> Lorem ipsum dolor sit amet, 
	
	consectetur adipiscing elit. 

	Maecenas dapibus orci 
	convallis 
	libero pharetra, gravida pharetra dolor fermentum. 
	
	pellentesque. Nam dapibus molestie nunc 
	<script> console.log("Hello")</script></p>
	```
	we would get two different results depending on whether we used `textContent` or `innerText`:

	```
	const p = document.querySelector('#special')

	p.innerText
	//Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas dapibus orci convallis libero pharetra, gravida pharetra dolor fermentum. pellentesque. Nam dapibus molestie nunc

	p.textContent
	// "Lorem ipsum dolor sit amet, 
	
	consectetur adipiscing elit. 

	Maecenas dapibus orci 
	convallis 
	libero pharetra, gravida pharetra dolor fermentum. 
	
	pellentesque. Nam dapibus molestie nunc 
	console.log("Hello")
	"
	```
* `.innerHTML`: returns everything as a string including the inside HTML elements and tags. You can add a tag and text directly into the HTML using this tag as well. 
	* when adding text (for ex) `innerHTML` is able to read tags and code for what they are (i.e. a `<strong> This is a bold tag</strong>` will appear as a bold text if innerHTML is used but innerText will simply literally write out that text, including the `<strong>` tags because it doesn't recognize them as tags) 

<br>

<a name="changingElements" class="changingElements"></a>

C. <ins>CHANGING / ADDING / REMOVING ELEMENTS: (parents, children, siblings)</ins>  

`createElement` will create a new HTML element
```
const newh2 = document.createElement('h2')

//a new (empty) <h2></h2> element will be created
// you can select and edit/add to that new element too

newh2.innerHTML = "I <b>love</b> animals"

// <h2>I <b>love</b> animals</h2>
```

`.getAttribute( );` this will retrieve the given element  
`.setAttribute( );` this can take two arguments. the first is the selected class and the second is the desired replacement/edit (note that if you use this to replace a class it will remove the first/original class, not just add it in)
```
var link = document.querySelector("a");

link.getAttribute("href");     //"www.google.com" 
link.setAttribute("href", www.dogs.com);

//<a href = www.dogs.com> I am a link</a> 

var img = document.querySelector("img");    
img.setAttribute("src", "odie.png");

//<img src="odie.png">; 
```
`Data- **` attributes: allow storage of extra info on  standard HTML elements w/o hacks of extra properties
* `Data-key` is a data attribute that links a key to an identifier (i.e. a number) [see Drum Kit Project in #Javascript30 course]

`.appendChild()` is used to add an element the child of the selected element. (to continue with the above example for 'createElement'...)  
```
h1.appendChild(newh2)
```
this will add the newh2 element as a child to the h1 element on the page. Note it will add the child to the end of whatever section it is added to (if there are multiple child elements it will be the last child element in that section) 

`.append` can insert multiple elements at once (unlike `.appendChild`) and add them to the end of the given/selected element
```
firstP.append(i,newLi)
```

`.prepend` similiar to `.append` but it will add the elements to the beginning of the selected element

`.removeChild` will remove the child of any specified parent (the parent has to be the parent of the selected child, of course)
```
ul.removeChild(li)
```

`.remove` works the same as `.removeChild` except it does not require a parent element to be specified;
```
h1.remove()
```

`.insertBefore` will add a new element to the page before the selected element. You must have the parent element identified in order to make this work properly. 
```
parentUl.insertBefore(newLi, firstLi)

//this will insert the newLi within the parent element 'parentUl' before the second paramenter (firstLi)
```
`.insertAdjacentElement` (similar to `.insertBefore`) takes 2 arguments (including a specified 'position') with the following sytax:
```
targetElement.insertAdjacentElement(position, element);

li.insertAdjacentElement('beforebegin', ul)
```
* the possible positions are: 
	* 'beforebegin': before targetElement itself 
	* 'afterbegin': inside targetElement, before 1st child 
	* 'beforeend': inside targetelement, after last child 
	* 'afterend': after targetElement itself

`.parentElement` will target the 'parent' of any element that you specify (i.e. whatever the selected element is inside of).  
Below you can see by requesting the parentElement of the `<li>` you get the `<ul>`. And so on, you can request the parentElement and it will retrieve the parent of whatever requested (until there are no more requested/available, i.e. after `<html>` there are no more elements to select and it would result in `null`)
```
const elementLi = document.querySelector('li')

elementLi.parentElement
// <ul>...</ul>

elemntLi.parentElement.parentElement.parentElement
//<html>
	<head>...</head>
	<body>...</body>
</html>
```
`.children` will select the children of any given element selected (i.e. whatever is inside of the given element). In other words, it looks inside the given element or downwards (instead of upwards in the case of `parentElement`).  
Using the above example,
```
const elementUl = document.querySelector('ul')

elementUl.children
// <li>...</li>
```
`.nextElementSibling` will target the next/immediately-following 'sibling' of any given element (i.e. the next element on the same 'level' as the given element)
```
const elementLi = document.querySelector('li')

elementLi.nextElementSibling
// <li>Second Li</li>
```
`.previousElementSibling` will target the previous 'sibling' of any given element
```
const elementLi = document.querySelector('li')
const thirdLi = elementLi.nextElementSibling.nextElementSibling

thirdLi.previousElementSibling
// <li>Second Li</li>
```


<ins>EVENTS</ins> 

Events make things interactive (for ex clicking a button, hovering over a link, etc).  

* Process: first you select an element and then you add an event listener 

	"Listen for a click on this `<button>`"   
	"Listen for a hover event on the `<h1>`" 

`.addEventListener` is used very often and there are two parts: 

1. Type of event that you want to listen for 

2. The code you want to run when the event happens 

	Ex: display a message when a button has been clicked: 
	```
	<button>Click Me</button>   
	<p>No one has clicked me yet</p> 

	var button = document.querySelector("button");    
	var paragraph = document.querySelector("p"); 
	```
SETUP CLICK LISTENER 
```
button.addEventListener("click", function() {    
	paragraph.textContent = "Someone clicked the button!"; 
	});   
```
You can have more than one 'listener' on an element.
Note: it is useful to to the keyword 'this' to separate functions and connect click listeners (see Colt's JS course in Section15 "The Event Object") 

KEY EVENTS

1. Keypress: pressing a key down and releasing

2. Keyup: any key that is released after being pressed down. 

3. Keydown: any key that is pressed down (on each, original key down) it will be logged in the console.  

FORM EVENTS	
(Colt's JS course Section 15 "Form Events & PreventDefault)  



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
	```
	let favSong = "Surfin' USA"
	```
	you cannot select the 'S' and change it to 'D' (for ex) as you can in other languages (`favSong[0] = "D"`) is invalid

	you can remove characters `let gibberish = "abcdefg"` as such: 
	```
	gibberish[gibberish.length -1]
	// this will remove 'g' resulting in gibberish = "abcdef"
	```

<a name="stringMethods" class="stringMethods"></a>

<ins>String Methods</ins> are built in actions that can be perfomed on or with a particular string (such as: search w/in a string, replace parts, change case). You must add the `( )` for the method to work

* `.toUpperCase()` | `.toLowerCase()`    
	```
	let msg = "you are grounded"
	```
	you can use `msg = msg.toUpperCase()` resulting in 
	```
	msg = "YOU ARE SO GROUNDED"
	```
* `.trim()`   
	```
	let color = "     purple"
	```
	you can use `color.trim();` resulting in 
	```
	color="purple";
	```
	Some methods accept arguments that modify their behavior. Arguments are passed inside of `( )`

* `.indexOf()` finds the index of an item in an array (it’s location in an array). Index starts at 0

	* `“hello”[0]` will produce: “h” (requests/calls for the character in the  0-position) 

 	* `“hello”[4]` will produce: “o” (requests/calls for the character in the 4-position) 

	* Inputting `“The Beatles”[4]` will produce: “B” 

* `slice()` accesses parts of a string (or array) using it's index
	* in an array you can use `slice()`   
		```
		Var fruits = [“banana”, “orange”, “lemon”, “apple”, “mango”];    
		var citrus = fruits.slice(1, 3);
		```  
		this will 'slice' the fruits array from index 1 and end the slice at index 3 resulting in 
		```
		citrus = [“orange”, “lemon”]

		note var fruits remains the same/ original variable: 
		var fruits = [“banana”, “orange”, “lemon”, “apple”, “mango”]`
		```
	 

	* in a string you can use `slice()`   
		```
		"baseball".slice(4)
		```
		will start a slice at index[4] and continue to the end resulting in 
		```
		"ball"
		``` 
		Another example is:
		```
		"superhero".slice[0,5]
		```
		will start a slice at index[0] and end the slice at index[5] resulting in 
		```
		"super"
		```

* `.replace()`   
	```
	var baseball = 'baseball is entertaining'.replace('entertaining', 'ok')
	``` 
	will result in 
	```
	baseball = "baseball is ok"
	```

Here's the [MDN page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) listing possible string methods (on the left side)

<ins>String Template Literals</ins> allow embedded expressions which will be evaluated and turned into a resulting string

```
I counted ${3+4} sheep;
// "I counted 7 sheep"
```
* use backticks ` (not single quotes) with this notation ${ }

	```
	let animal = "pig"    
	let sound = "oink"   
	`${animal} says ${sound}`
	```
	(* these are backticks on each end not quotes)

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

<a name="callStack" class="callStack"></a>

### CALL STACK	
The call stack is the mechanism in the JS interpreter uses to keep track of its place in a script that calls multiple functions. It is how JS 'knows' what functino is currently being run and what functions are called from within that function etc
* 'call' refers to function calls (which func are being called or have been called, etc)
* 'stack' is a data structure term similar to a stack of books or plates where the last, most recent thing added to the stack, or pile, is what will be retrieved first.
* How it Works:
	* when a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
	* any functions that are called by that function are added to the call stack further up, and run where their calls are reached
	* when the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing


<ins>Debugging</ins>
* debugging is useful to breakdown the call stack and identify problem areas within your code, step by step.
* The Process:
	* in the console, go to the 'source' tab while in the desired page you want to debug (JS in this case).
	* you can click on any of the numbered rows (to the left of the code) to select a 'breakpoint' where you would like the code to stop/pause
	* then on the right-hand side you have a 'debugger menu' where you can move forward, step by step, to watch how the functions are being called thru the call stack, etc  

<ins>Asynchronous Callbacks</ins>  

* JS is single threaded (so it only works on one thing at a time before moving on to the next task/code)
* How can we work around this potential 'problem'? How do you get your code to continue in JS or get JS to 'multitask'? The workaround is the browser
	* for ex: if you had a delay timer of 3 seconds, and JS only works on one line at a time, how do you get the code to continue or have JS monitor the timing AND get the next code out (so your app or page doesn't freeze until the timer is finished)?  
	simple answer: it's the *browser*!
* The Brower:
	* browers come with Web APIs that are able to handle certain tasks int eh background (like making requests or setTimeouts)
	* the JS call stack recognizes these Web API functions and passes them off to the brower to take care of 
	* Once the brower finishes those tasks they return and are pushed onto the stack as a callback  

<ins>Promises</ins>  
(Section 16 in Colt's JS Course)  
A pattern for writing async code; it's an object representing the eventual completion or failure of an asynchronous operation.  
Basic syntax example:
```
const newDog = new Promise((resolve, reject) => {
	const rand = Math.random();
	if(rand < .5) {
		resolve();
	} else {
		reject()
	}
})
newDog.then( => {
	console.log('Yeah! We got a dog!');
})
newDog.catch( => {
	console.log('Oh no! We don't get a dog!');
})
```
* a Promise (capital 'P') has a status of 'resolved' or 'rejected' (and if neither is chosen it has a status of 'pending').
* the `.then` of a Promise will run when the Promise is 'true' or 'resolved'
* the `.catch` will run when the Promise is 'false' or 'rejected'  
* Note: you can chain Promises together which helps keep the code DRY

`Promise.all` returns a Promise which is stored in an array of individual Promises  
* it helps to keep your code DRY
* the Promise.all will only run once all the other Promises have run

<hr>

<a name="requests" class="requests"></a>

### HTTP Requests

(Find more info in Colt's JS course Section 17) 

<ins>AJAX</ins> : Asynchronous Javascript and XML  
* XML is the original notation to send requests via JS (not as widely used nowadays)  
* it doesn't support promises (so lots of callbacks)
* note the capitalization rules (XMLHttpRequests) and clunky/lengthy syntax (difficult to remember)
* Read more on [MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) 

```
const firstReq = new XMLHttpRequest();
firstReq.addEventListener('load', function() {
	console.log('it worked!);
	const data = JSON.parse(this.responseText);
	console.log(data);
});
firstReq.addEventListener('error', () => {
	console.log('error!);
});
firstReq.open('GET', 'https://www.google.com');
firstReq.send();
console.log('Request Sent!');
```

* Fetch API (it's a method)
	* this is the newer way to make requests via JS
	* it supports Promises
	* since it's newer, it's not supported by some browsers
	* fetches can be chained together
	* it takes one mandatory argument (the path to the resource you want to fetch). It returns a Promise that resolves to the Response to that request, whether it is successful or not. you can also optionally pass in an init options object as the second argument. Read more at [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)  
* Axios
	* this is an external library (so it has to be added to your documents to be able to access it)
	* it's an even easier way than fetch (in a lot of ways) to make requests

<ins>AJAJ</ins>: Asynchronous Javascript and JSON (JS Object Notation)  
* JSON is another notation (it looks a lot like JS but it's not actually JS; however it is easy to translate between the two)  

Using `async` and `await` [keywords](#keywords) with Requests (find more info on these keywords in the 'Functions' section of this document)

