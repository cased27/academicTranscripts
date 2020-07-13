# JAVASCRIPT

* JS is the 'verb' of a webpage 
* comment out using `//` (double slash)
* clear the console using the function `clear()`
* 'inspect' the page and use the console (developer's tool)
* docs are saved with ' .js ' 


<a name="tableOfContents" class="tableOfContents"></a>

### <u>TABLE OF CONTENTS</u>
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

| | 
|---------:|
|[Table of Contents](#tableOfContents)| 

<hr>
<a name="pDatatypes" class="pDatatypes"></a>

### PRIMITIVE DATATYPES

Different categories of data

* [NUMBERS](#numbers): whole number (4) fraction (9.3) negative (-10); All numbers are treated the same 

* [STRINGS](#strings): words or numbers inside quotations (single or double) like "Hello World" or "43"

* [BOOLEAN](#boolean): either TRUE or FALSE 

* NULL: variables that are explicitly <em>nothing</em>
	* used often in games for 'game over' or the end
	<br>var currentPlayer = “charlie”; 
	<br>currentPlayer = null; // game over 
				
* UNDEFINED: variables that are declared but not initialized/ defined; it’s a ‘nothing’ value but only because it hasn’t been declared <em>yet</em>
	* var name;  OR var age;
	<br>both undefined; they are declared but no value is assigned (like var name = “Helen”) (in the console you'd get‘undefined’ because they have no value assigned to them) 
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
<u>VAR vs LET vs CONST</u><br>
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

<hr>
<a name="methods" class="methods"></a>

### METHODS

* `alert()` pops up a message to the user in a pop-up window 
* `prompt()` can get input from the user 
	* `prompt(“what is your name?”);`  
	will send this question thru (with an answer box) in a pop-up window, allowing the user to answer. The answer will appear in the console 
* `console.log()` prints out whatever text is requested through the console (not on the page itself) 

<hr>
<a name="conditionals" class="conditionals"></a>

### CONDITIONALS

<hr>
<a name="loops" class="loops"></a>

### LOOPS

<hr>
<a name="functions" class="functions"></a>

### FUNCTIONS

<hr>
<a name="arguments" class="arguments"></a>

### ARGUMENTS

<hr>
<a name="arrays" class="arrays"></a>

### ARRAYS

<hr>
<a name="objects" class="objects"></a>

### OBJECTS

<hr>
<a name="numbers" class="numbers"></a>

### NUMBERS & NUMERIC OPERATIONS

The JS Console can be used like a calculator
* different operations are possible ( + - * / )
* Order of operations / (PEMDAS) Parenthesis, Exponents, Multiplication, Division, Addition, Subtraction 

<u>Modulo</u>: also called the remainder operator or Modulus is represented by ' % '

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
 
<hr>
<a name="strings" class="strings"></a>

### STRINGS

Strings are all/any content within quotation marks 

Single or double quotes are OK (but they must match) 

* “hello world” OR ‘hello world’ are VALID 
* “hello world’ is INVALID; they need to match 
* “I can’t stop eating candy” is VALID; you can have a single quote within a double 
* ‘I can’t stop’ is INVALID; the console reads that the sting ends after can 

<u>Concatenation</u>: adding strings together 
* “hi” + “goodbye” = “higoodbye” 
* “hi” + “ goodbye” = “hi goodbye” (adding space before “ goodbye” 

<u>Escape Characters</u>: start with `\` (backslash) and allow you to add special characters 

* Adding `\` allows you to add special characters (like quotations that would normally be read by the console) without allowing the console to read it as something else 
	* “she said \”goodbye!\”” will produce: she said “goodbye!” 
	* “she said ”goodbye!”” will be INVALID 
* To add an actual backslash to the code you would do a double backslash 
“Hello world. \\” will produce: “Hello World. \” 

<u>Length Property</u>: every string has a length property, starts counting at 1 

* `“my favorite number is: 1234”.length` is 27 characters long (includes spaces)

* Access individual characters using `[ ]` and an index: it will call the particular position in a string of the number requested starting at “0” (so the first character is at 0) 

	* `“hello”[0]` will produce: “h” (requests/calls for the character in the  0-position) 

 	* `“hello”[4]` will produce: “o” (requests/calls for the character in the 4-position) 

	* Inputting `“The Beatles”[4]` will produce: “B” 

<hr>
<a name="boolean" class="boolean"></a>

### BOOLEAN
These statements can be used to combine the initial T/F statement to create more complex statements that also evaluate to T/F 
<br>

<u>Comparison Operators</u> <br>
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

<br><u>Double Equals v Triple Equals (== vs ===)</u>

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

<br><u>Logical Operators</u> (assuming below x = 5 and y = 9)

| Operator | Name | Example            | Result | Explanation                  |
|:--------:|:----:|--------------------|:------:|------------------------------|
|    &&    | AND  | x < 10 && x !== 5  | false  | requires both sides to be T  |
|   \|\|   |  OR  | y > 9 \|\| x === 5 |  true  | requires 1 side to be T      |
|    !     | NOT  | !(x===y)           |  true  | gives the opposite of result |

<br><u>Truthy / Falsy</u> 

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

<hr>
