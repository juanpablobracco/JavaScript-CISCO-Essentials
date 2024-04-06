JavaScript Essentials 1 y 2 whit certification
Cisco - https://skillsforall.com



 SECTION 2 - Variables, Data types, type casting, and comments
--------------------------------



TEMAS RELEVANETES DEL CAPITULO:

-Initialzing variables, 
-Devlarations and strict mode,
-constants
-Variable shadowing: It means that we can declare a global variable and a local variable of the same name.

-SCOPE: 
-----------------

    (Local or global en relacion con estar dentro de una funcion declarada. En este punto la declaracion "LET" or "VAR" se comportan de diversas maneras dependiendo de si se aclara al inicio si se utilizara el "STRICT MODE DE VANILLA JAVA") :

    Se entiende por SCOPE al alcance o seccion del codigo en el que una "variable" tiene alcance, puede ser global, es decir que una variable y su valor tendra uso durante todo el codigo, o bien puede ser "local", y asi la misma tiene un alcance utilitario limitado a un determinado "blocke" de codigo.

    Ejemplo de GLOBAL SCOPE

    let counter;
    console.log(counter); // -> undefined
    {
        counter = 1;
        console.log(counter); // -> 1
    }
    counter = counter + 1;
    console.log(counter); // -> 2

    -------------------------------------------------------
    EJEMPLO DE LOCAL SCOPE

    let height = 180;
    {
        let weight = 70;
        console.log(height); // -> 180
        console.log(weight); // -> 70
    }
    console.log(height); // -> 180
    console.log(weight); // -> Uncaught ReferenceError: weight is not defined



2.1 DATA TYPES AND TYPE CASTING:
-------------------

In JavaScript, data types are divided into PRIMITIVE (or simple) and COMPLEX (or composite). Among the primitive types, we can find NUMBERS and STRINGS of characters, while the complex types include, for example, ARRAYS and OBJECTS.

LITERALS: 
------------------

Are a way of noting specific values (data) in the program code.
    let  year  =  1990; DECLARATION OF THE VARIABLE, AND INICIALIZACION CON EL VALOR 1990; AQUI "1990" ES UN LITERAL QUE REPRESENTA UN NUMERO EN EL LUGAR DE LA INICIALIZACION DE LA VARIABLE.
    console.log(year);  //  ->  1990
    console.log(1991);  //  ->  1991
    console.log("Alice");  //  ->  Alice

TYPEOF OPERATOR:
--------------
an OPERATOR is a symbol or name that represents some action to be performed on the indicated arguments. For example, the + symbol is a two-argument operator representing summation.

The TYPEOF operator just mentioned is unary (it takes only one argument) and informs us of the type of data indicated as a given argument.

All possible return values of the typeof operator are:

    "undefined" P
    "object"
    "boolean" P
    "number" P
    "bigint" P
    "string" P
    "symbol" P
    "function"

    let year = 1990;
    console.log(typeof year); // -> number
    console.log(typeof 1991); // -> number

    let typeOfYear = typeof year;
    console.log(typeOfYear); // -> number
    console.log(typeof typeOfYear); // -> string


## PRIMITIVE DATA TYPES:
--------------------
 is a type of data whose values are atomic. This means that the value is one, indivisible element.
(Boolean, Number, BigInt, String, Symbol, and undefined.)

### Boolean:
(TRUE OR FALSE)
Mainly used as a conditional expression.
    (control flow statements, flag etc)
FLAG (variable that signals something that can be either present or absent, enabled or disabled)

let isDataValid = true;
let isStringTooLong = false;
let isGameOver = false;
continueLoop = true;
   
    console.log(false); // -> false
    console.log(typeof false); // -> boolean
    console.log(isDataValid); // -> true
    console.log(typeof isDataValid); // -> boolean

NOT, AND, and OR (the symbols !, && and || correspondingly)


### Number:
 represents both real numbers (e.g. fractions) and integers.
  the integer values should be limited in JavaScript to the range from -(253 – 1) to (253 – 1)
Numbers allow for all typical arithmetic operations, like addition, subtraction, multiplication, and division.
if a literal describing a number is preceded by an appropriate prefix, we can present it in hexadecimal (0x…), octal (0o...) or binary (0b...) form
    let a = 10; // decimal - default
    let b = 0x10; // hexadecimal
    let c = 0o10; // octal
    let d = 0b10; // binary
    
    console.log(a); // -> 10
    console.log(b); // -> 16
    console.log(c); // -> 8
    console.log(d); // -> 2
    
    let x = 9e3;
    let y = 123e-5;
    console.log(x); // -> 9000
    console.log(y); // -> 0.00123

In addition to regular numbers in JavaScript, we use three additional special values, which are: Infinity, -Infinity and NaN (not a number)
    let a = 1 / 0;
    let b = -Infinity;
    
    console.log(a); // -> Infinity
    console.log(b); // -> -Infinity
    console.log(typeof a); // -> number
    console.log(typeof b); // -> number
    
    let s = "it's definitely not a number";
    let n = s * 10;
    console.log(n); // -> NaN
    console.log(typeof n); // -> number


### BigInt:
 The BigInt type is not used too often. It allows us to write integers of virtually any length. For almost any normal numerical operations, the Number type is enough, but from time to time we need a type that can handle much bigger integers.

### String:
 The String type represents a sequence of characters forming a piece of text. Common operations on texts include concatenation, extraction of the substring, and checking the length of the string. 

string interpolation:
 . It allows you to treat a character string as a template, in which you can place values in selected places, such as those taken from variables

    let country = "Malawi";    
    let continent = "Africa";
    
    let sentence = ` ${country} is located in ${continent}.`;
    console.log(sentence); // -> Malawi is located in Africa.   


### Undefined:
 It’s the default value that all variables have after a declaration if no value is assigned to them. You can also assign the value undefined to any variable, but in general, this should be avoided, because if we need to mark a variable as not holding any meaningful value, we should use null.

### Symbol:
 Symbols are a form of identifier that are guaranteed to be unique.

### Null:
 is used to indicate that the variable does not contain anything, and most often it is a variable that is intended to contain values of complex types.
 we can assume that the undefined value is assigned to uninitialized variables automatically, but if we want to explicitly indicate that the variable does not contain anything, we assign it a null value. 

 
### METHODos
---------------

 is a special kind of function that belongs to an object. Objects are complex data types, which can consist of many values (stored in properties) and methods. If you want to call the method of an object, you write the name of the method after a dot. Does this remind you of something? This is exactly the notation you use when calling console.log. The console object has many other methods besides the log method, such as time and timeEnd (which can be used to measure time).

 All data of primitive types such as Number, BigInt, Boolean, or String have corresponding objects to which they can be converted. Each of these objects will have methods designed for a specific data type. At this point, we come to another concept, that is, autoboxing. If a dot appears after a literal representing a primitive type, or after a variable containing this type of data, the JavaScript interpreter tries to treat this value as an object and not a primitive. For this purpose, it converts the primitive to the corresponding object on the fly, which has the appropriate methods (i.e. it performs autoboxing). A bit confusing, isn't it? Fortunately, in order to use methods, we don't have to understand it exactly – it's enough to follow the given convention.+

 let river = "Mekong";
 let character = river.charAt(2);
 console.log(character); // -> k

 length: property, returns the number of characters in a string;

 charAt(index): method, returns the character at the "index" position in the string (indexes start from 0);

 slice(beginIndex, [optional] endIndex): method, returns a new string that is created from the characters between beginIndex (included) and endIndex (excluded); if endIndex is omitted, then the new string is from beginIndex to the end of the string;

 split(separator, [optional] limit): method, splits the string into substrings whenever a separator is found in that string, and returns an array of those substrings (we will say a few words about arrays in a moment), while an optional limit limits the number of substrings added to the list.

 
![Alt text](35974224f364297500dfea4d1205890bebc439f0.png)





### Type conversions
---------------


 Using literals is not the only way to create variables of the given primitive types. 
 Most of these functions can be called without any arguments. In such a situation:

 the function String will by default create and return an empty string – primitive "";
 the function Number will by default create and return the value 0;
 the function Boolean will by default create and return the value of false.
 
    const str = String();
    const num = Number();
    const bool = Boolean();
    
    console.log(str); // ->
    console.log(num); // -> 0
    console.log(bool); // -> false
    
    const big1 = BigInt(42);
    console.log(big1); // -> 42n
    
    const big2 = BigInt(); // -> Uncaught TypeError: Cannot convert undefined to a BigInt



 #### Conversions:
 
    Const num = 42;
   
    const strFromNum1 = String(num);
    const strFromNum2 = String(8);
    const strFromBool = String(true);
    const numFromStr = Number("312");
    const boolFromNumber = Boolean(0);

    console.log("strFromNum1", strFromNum1, typeof strFromNum1);
    console.log("strFromNum2", strFromNum2, typeof strFromNum2);
    console.log("strFromBool", strFromBool, typeof strFromBool);
    console.log("numFromStr", numFromStr, typeof numFromStr);
    console.log("boolFromNumber", boolFromNumber, typeof boolFromNumber);
 

    let str = "text";
    let strStr = String(str);
    console.log(`${typeof str} : ${str}`); // -> string : text
    console.log(`${typeof strStr} : ${strStr}`); // -> string : text
    let nr = 42;
    let strNr = String(nr);
    console.log(`${typeof nr} : ${nr}`); // -> number : 42
    console.log(`${typeof strNr} : ${strNr}`); // -> string : 42
    
    let bl = true;
    let strBl = String(bl);
    console.log(`${typeof bl} : ${bl}`); // -> boolean : true
    console.log(`${typeof strBl} : ${strBl}`); // -> string : true
    
    let bnr = 123n;
    let strBnr = String(bnr);
    console.log(`${typeof bnr} : ${bnr}`); // -> bigint : 123
    console.log(`${typeof strBnr} : ${strBnr}`); // -> string : 123
    
    let un = undefined;
    let strUn = String(un);
    console.log(`${typeof un} : ${un}`); // -> undefined : undefined
    console.log(`${typeof strUn} : ${strUn}`); // -> string : undefined
    
    let n = null;
    let strN = String(n);
    console.log(`${typeof n} : ${n}`); // -> object : null
    console.log(`${typeof strN} : ${strN}`); // -> string : null



 ##### Conversion to Number

    console.log(Number(42)); // -> 42
    
    console.log(Number("11")); // -> 11
    console.log(Number("0x11")); // -> 17
    console.log(Number("0o11")); // -> 9
    console.log(Number("0b11")); // -> 3
    console.log(Number("12e3")); // -> 12000
    console.log(Number("Infinity"));// -> Infinity
    console.log(Number("text")); // -> NaN
    
    console.log(Number(14n)); // -> 14
    console.log(Number(123456789123456789123n)); // - > 123456789123
    456800000
    
    console.log(Number(true)); // -> 1
    console.log(Number(false)); // -> 0
    
    console.log(Number(undefined)); // -> NaN
    
    console.log(Number(null));// -> 0


 ##### Conversion to Boolean
 The value false is always returned for:

    0,
    NaN,
    empty string,
    undefined,
    null
 Any other value will result in true being returned.


 #####  Conversion to BigInt

 let num = 23;
let num1 = Number(num);
let str = "23";
let str1 = String(num); 
let bool = true;
let bool1 = Boolean(1);
let bigI = BigInt(23);
let u1 = undefined;

console.log(`${num} [${typeof num}]`);
console.log(`${num1} [${typeof num1}]`);
console.log(`${str} [${typeof str}]`);
console.log(`${str1} [${typeof str1}]`);
console.log(`${bool} [${typeof bool}]`);
console.log(`${bool1} [${typeof bool1}]`);
console.log(`${bigI} [${typeof bigI}]`);
console.log(`${u1} [${typeof u1}]`);++





## Complex data types
-------------------------

objects and arrays

### Object
 Objects have many applications in JavaScript. One of the most basic, and at the same time the only one that we will deal with now, is to use it as a structure known in computer science as a record. A record is a collection of named fields. Each field has its own name (or key) and value assigned to it.

 let testObj = {
 nr: 600,
 str: "text"
 };
 console.log(typeof testObj); // -> object

 console.log(testObj.nr); // -> 600
 console.log(testObj.str); // -> text 


 We can modified with the same dotation:


 console.log(user1.name); // -> Calvin
 console.log(user2.name); // ->  Mateus
   
 console.log(user1.age); // -> 66
 user1.age = 67;
 console.log(user1.age); // -> 67
   
 console.log(user2.phone); // -> undefined
 user2.phone = "904-399-7557";
 console.log(user2.phone); // -> 904-399-7557


 the delete operator is used for this.

 console.log(user2.phone); // -> 904-399-7557
 delete user2.phone;
 console.log(user2.phone); // -> undefined



 ### Array
 An array, like an object, is a complex data type that can be used to store a data collection. Similar to an object, the stored data (the values) can be of any type. The difference between these structures is that in an array we only store values, without the associated names (i.e. the keys).



 let days = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];
 console.log(days[0]); // -> Sun
 console.log(days[2]); // -> Tue
 console.log(days[5]); // -> Fri
   
 days[0] = "Sunday";
 console.log(days[0]); // -> Sunday
   
 let emptyArray = [];
 console.log(emptyArray[0]); // -> undefined



 We also could add an empty element to an array:

 let animals = [];
 console.log(animal[0]);

 animals[0] = "OLI";
 animals[2] = "Pipi";
 console.log(animal[0]);
 console.log(animal[1]);
 console.log(animal[2]);

 We also can creat compound arrays with multiple braquets:

 let names = [["Olivia", "Emma", "Mia", "Sofia"], ["William", "James", "Daniel"]];
 console.log(names[0]); // -> ["Olivia", "Emma", "Mia", "Sofia"]
 console.log(names[0][1]); // -> Emma
 console.log(names[1][1]); // -> James
   
 let femaleNames = names[0];
 console.log(femaleNames[0]); // -> Olivia
 console.log(femaleNames[2]); // -> Mia




## 3 OPERATORS:
---------------------------
### Assigment, arithmetic and logical operators.

Comparison:
To check if the operands are equal, we can use either the identity (strict equality) operator === or the equality operator ==.

 console.log(10 === 5); // -> false
console.log(10 === 10); // -> true
console.log(10 === 10n); // -> false
console.log(10 === "10"); // -> false
console.log("10" === "10"); // -> true
console.log("Alice" === "Bob"); // -> false
console.log(0 === false); // -> false
console.log(undefined === false); // -> false


The equality operator requires that they are only equal, and their types are not compared. So if the operands are of different types, the interpreter will try to convert them to numbers, for example, false will convert to 0, true to 1, undefined to NaN, null to 0, 10n to 10 and "123" to 123, etc.

If the operands has a NaN value the equality operator will return false.

 the nonidentity operator !== // returns true if the operands are not identical
 and the inequality operator. they are equal but of different types, or they are simply different
 
 != // returns true if the operands are different.

 <
 >
 <=
 >=
 => To construct arrow functions



 OTHERS:

 typeof
 instanceof == It is a binary operator that checks whether an object (left operand) is of some type (right operand).
 delete == It allows you to delete a selected field of the object whose name is indicated with an operand. - 
  delete user.age;

  Three operands operator:
 ternary == Based on the value of the first operand (true or false), the value of the second or third operand, respectively, is returned

 i.e. 
 console.log(true ? "Alice" : "Bob"); // -> Alice
console.log(false ? "Alice" : "Bob"); // -> Bob
  
  Ternary opèrator using as a first operand a comparison of two numbers. This conditional expresion will return the "True or false" that the "Ternary" need to operate and return one or the other value.

 let name = 1 > 2 ? "Alice" : "Bob"; console.log(name); // -> Bob



## Precedence
-------------------

in what order will the interpreter perform them? This will of course affect the final result of the operators, so it is worth taking this into account when writing the instructions.

The JavaScript interpreter uses two operator properties to determine the sequence of operations: precedence and associativity. Precedence can be treated as a priority, with some operators having the same precedence (e.g. addition and subtraction). Associativity allows you to specify the order of execution if there are several operators with the same priorities next to each other.

he use of parentheses not only forces the order of actions, but also increases the readability of the code (the person reading it does not have to wonder what and in what order it will be done).

The full list of operators and properties can be found on the MDN pages.


SECTION 3 – Interacting with the user
---
### 3.2.2 Dialog box

 All of them are popup windows (or modal windows)

 #### Alert dialog box:   alert() method
 or window.alert

 alert("Hello, World!")
 window.alert("Hello, World! for the second time");
 alert(4 * 7);
 alert(true);
 alert("text 1", "text 2"); // only "text 1" will be displayed


 #### Confirm dialog box:

 The difference between alert and confirm is that the confirm dialog box displays two buttons, the OK button and the Cancel button.

 Returning TREU or FALSE corresponding to the accept button or the cancel one.

 let decision = window.confirm("Is it OK?");
 console.log(decision);
 
 Another e.i.,
 let remove = confirm("Remove all data?");
 let message = remove ? "Deleting Data" : "Cancelled"
 
 console.log(message); 

 // at this way we will get assigned the response of the user to deploid what the program have to do next. Utilazing conditional operator.


 #### Prompt dialog box
 it contains the OK and Cancel buttons, but it also contains a single-line text field that allows the user to input text. 

 the prompt accepts an optional parameter as a message that will be displayed.

 e.i.
 let name = window.prompt("What is your name?", "John Doe");
 name = name ? name : "anonymous";
 
 let age = prompt("Hello " + name + " how old are you?");
 alert(name + " is " + age + " years old");

### PRACTICE
 Using everything you’ve learned up until this point, write a script that asks a user about the width, height, and length of a box, then calculate and return to the user the volume of this box.


 alert("Let's calculate that box volume...");

let width = prompt("Whats the width?");
let height = prompt("Whats the height?");
let length = prompt("Whats the length?");

volume = width * height * length;
 

alert(`The volume of the box is:  ${volume}`);


####
Let's go back to our contact list. After some recent tweaks (i.e. using an array and objects) it is actually starting to look like a list. However, one quite serious problem remained. Changing data in the list, such as adding a new contact, has to be provided for right away in the program code. What if we want to give the user the ability to enter the data of the added contact while the program is running? Modify the program to add, at the end of the list, not the contact, which is given in the code, but the one which the user will give during the program run. Use the prompt method to do this. At the end, display the first and the last contact from the list.


SOLUTION:

let contacts = [{
name: "Maxwell Wright",
phone: "(0191) 719 6495",
email: "Curabitur.egestas.nunc@nonummyac.co.uk"
}, {
name: "Raja Villarreal",
phone: "0866 398 2895",
email: "posuere.vulputate@sed.com"
}, {
name: "Helen Richards",
phone: "0800 1111",
email: "libero@convallis.edu"
}];

// Requesting the current user data to add to our storage.

let newName = prompt("Whats your name?");
let newPhone = prompt("Whats your phone number?");
let newEmail = prompt("Whats your email adress?");

// Building a new array with the data provided.

let newContact = {
    name: newName,
    phone: newPhone,
    email: newEmail
};

// Adding to the end position of the "contacts" object the new contact data provide by the user.

contacts.push(newContact)

// Counting the current object length to print the last regardless of the number of contacts

let last = contacts.length - 1;

//Printing the first and last contact of our data base.

console.log(`${contacts[0].name} / ${contacts[0].phone} / ${contacts[0].email}`);
console.log(`${contacts[last].name} / ${contacts[last].phone} / ${contacts[last].email}`);


# CONTROL FLOW - CONDITIONAL EXECUTION AND LOOPS

## Conditional execution:
### Conditional statements:

We can imagine our program as a tree that starts from the trunk and gradually splits it into subsequent branches. The trunk is the beginning of the program, and each conditional instruction is a reflection of a new branch. Conditional instructions are executed on the basis of the user's decision, results of previous calculations, or other information that the program will take into account. JavaScript provides a few ways to branch code execution.

### IF

 it checks a given condition, and depending on its Boolean value, either executes a block of code, or skips it. The syntax looks like this:

 if (condition) {
    block of code
 }

 e.i.
 let isUserReady = confirm("Are you ready?");
 console.log(isUserReady);
 if (isUserReady) {
    alert("User ready!");
 }


 let userAge = 23;
let isFemale = false;
let points = 703;
let cartValue = 299;
let shippingCost = 9.99;
 
if (userAge > 21) {
    if (cartValue >= 300 || points >= 500) {
        shippingCost = 0;
    } //true - (false OR True)True = shippingCost = 0.
}
 
console.log(shippingCost); --> 0


Podemos reducir la conditional statement to the next logical expression:

if (userAge > 21 && (cartValue >= 300 || points >= 500)) { //True && True(False||True )
    shippingCost = 0;
}


### IF ELSE

if (condition) {
condition - true code
} else {
condition - false code
}

e.i.
let isUserReady = confirm("Are you ready?");
if (isUserReady) {
    console.log("User ready!");
} else {
    console.log("User not ready!");
}


### IF ELSE IF

if (conditions_1) {
  code
} else if (condition_2) {
  code
} else if (condition_3) {
  code
} else {
  code
}


e.i.

let number = prompt("Enter a number", 0);
 
if (number < 10) {
    alert("<10");
} else if (number < 30) {
    alert("<30");
} else if (number < 60) {
    alert("<60");
} else if (number < 90) {
    alert("<90");
} else if (number < 100) {
    alert("<100");
} else if (number == 100) {
    alert("100")
} else {
    alert(">100")
}


### Conditional operator

 It allows us to perform one of two actions based on the value of the first operand. Most often it is used as an alternative to the if ... else instruction when you want to assign one of two values to a variable, depending on a certain condition.

 let price = 100;
let shippingCost;
if (price > 50) {
    shippingCost = 0;
} else {
    shippingCost = 5;
}
console.log(`price = ${price}, shipping = ${shippingCost}`); // -> price = 100, shipping = 0


The same code rewritten using the conditional operator looks a bit easier.

let price = 100;
let shippingCost = price > 50 ? 0 : 5;
console.log(`price = ${price}, shipping = ${shippingCost}`); // -> price = 100, shipping = 0


The conditional operator returns the values of the second or third operand, but if they are complex expressions, it will calculate them first. You can use this fact to place the commands to be executed conditionally as these operands.

e.i. 
let start = confirm("Start?");
start ? alert("Here we go!") : console.log("Aborted");


However, it would make more sense to save the same piece of code in the following form:

e.i.
let start = confirm("Start?");
let message = start ? "Here we go!" "Aborted";
alert(message);


### SWITCH CASE statement:

It’s somewhat similar to nested if … else statements, but instead of evaluating different expressions, switch evaluates one conditional expression and then tries to match its value to one of the given cases. Here is the syntax of the switch statement:

switch (expression) {
    case first_match:
        code
        break;
    case second_match:
        code
        break;
    default:  
        code
}

After the colon, there is a block of code that will be executed when the expression is evaluated to this case value. The block of code optionally ends with the break keyword. 

Additionally, a special case named default can be present (by convention placed on the end of the switch statement; however, it isn’t required). The default case is executed when none of the cases matches the expression. The evaluation itself is made with a strict comparison operator (===) so not only must the value match, but also the type of case value and the expression.

e.i.

let gate = prompt("Choose gate: a, b, or c");
let win = false;
 
switch (gate) {
    case "a":
        alert("Gate A: empty");
        break;
    case "b":
        alert("Gate B: main prize");
        win = true;
        break;
    case "c":
        alert("Gate C: empty");
        break;
    default:
        alert("No gate " + String(gate));
}
 
if (win) {
    alert("Winner!");
}



### Practice

Exercise 2: Rewrite the code from the previous task, replacing if with a ternary conditional operator.

let numBingo = prompt("Enter a number", 0);


let message = (numBingo > 90 && numBingo < 110) ? "Bingo!" : "Miss";
alert(message)

Exercise 3: Write a simple calculator application. Ask the user for the following input, one by one: two numbers and a character representing a mathematical operation, one of "+", "-", "*", "/". If the user input is valid, calculate the result and show it to the user. If the user input is invalid, display a message that informs the user that an error has occurred.

Remember that the value returned by the prompt function is of the type string. You can use the Number.isNaN method to check if you get the correct number after conversion. For example, calling Number.isNaN(10) will return false, while Number.isNaN(NaN) will return true.

// Calculator application:
alert("Lets calculate");
let number1 = Number(prompt("Enter the first operand:", 10));
let operation = prompt("Enter the operation:", "+");
let number2 = Number(prompt("Enter the second operand:", 10));
let result = null;

switch (operation) {
    case "+":
        result = number1 + number2;
        break;
    
    case "-":
        result = number1 - number2;
        break;
        
    case "*":
        result = number1 * number2;
        break;
        
    case "/":
        result = number1 / number2;
        break;
    
    default:
        alert("Not a valid operation" + String(operation));
}

alert(`The result is = ${result}`);


e.i. Another way:
// Calculator application:
alert("Lets calculate");
let number1 = Number(prompt("Enter the first operand:", 10));
let operation = prompt("Enter the operation:", "+");
let number2 = Number(prompt("Enter the second operand:", 10));
let result;


if (!Number.isNaN(number1) && !Number.isNaN(number2)) {
    switch (operation) {
        case "+": result = number1 + number2; break;
        case "-": result = number1 - number2; break;
        case "*": result = number1 * number2; break;
        case "/": result = number1 / number2; break;
        default: alert("Not a valid operation : " + String(operation));
    }
} else {
    result = "Error: at least one of the entered values is not a number";
}

alert(result);

choice = prompt("What you want to do: 'first', 'last' or ad a 'new' contact", "new");



Scenario
During the last modification of the program with the contact list, we allow the user to add a new contact with the data entered by the user while the program is executing. Let's go a step further – try to modify the program so that the user has a choice of what they want to do with the list. They will have a choice of:

showing the first contact (first)
showing the last contact (last)
adding a new contact (new)
When adding a new contact, check if the user has entered all the necessary data. If at least one of the three values is missing (name, phone, or email) don't add the contact.

let choice;
let contacts = [{
    name: "Maxwell Wright",
    phone: "(0191) 719 6495",
    email: "Curabitur.egestas.nunc@nonummyac.co.uk"
}, {
    name: "Raja Villarreal",
    phone: "0866 398 2895",
    email: "posuere.vulputate@sed.com"
}, {
    name: "Helen Richards",
    phone: "0800 1111",
    email: "libero@convallis.edu"
}];

let oldLenght = contacts.length - 1;
choice = prompt("What you want to do: 'first', 'last' or ad a 'new' contact", "new");

switch (choice) {
        case "first": 
            alert("first contact data: " + contacts[0].name + " " + contacts[0].phone + " " +  contacts[0].email);
            break;
        case "last":
            alert("last contact data: " + contacts[oldLenght].name + " " + contacts[oldLenght].phone + " " + contacts[oldLenght].email);
            break;
        case "new":
            let newName = prompt("Whats your name: ", "Juan");
            let newPhone = prompt("Whats your phone: ", 10000);
            let newEmail = prompt("Whats your email: ", "juan@jjj.com");

            if (newName === Null or newPhone === Null or newEmail === Null) {
                Alert("All camps must be filled!)
            } else {
                let newContact = { 
                name: newName,
                phone: newPhone,
                email: newEmail 
                };
                contacts.push(newContact);
                alert("The new contact was stored!");
            
            };
            break; //Modificado ultima version a testear
            
        default: alert("Not a valid operation : " + String(operation));
    }

newLenght = contacts.length;
alert(newLenght);


... // nos falta en el codigo evaluar si algun campo ingresado en nuevo ha sido Null y desplegar un error Alert.


## LOOPS

Loops are the second form of flow control statement.

While conditional statements are able to change code behavior (allowing us to decide during program execution whether a certain piece of code is to be performed or not), loops are an easy way to repeat any fragment of the code as many times as we want, or until some condition is met. 

We can loosely split them into two categories:

    loops that are repeated a given number of times;

    loops that continue until some condition is met.


### WHILE LOOP


while(condition) {
    block of code
}

Remember that the variable that is tested in the while condition should be initialized beforehand.

e.i.

let n = 0;
while(n < 91) {
    console.log(n); // -> 0, 10, 20, 30, 40, 50, 60, 70, 80, 90
    n += 10;
}

e.i. 

let isOver = false;
let counter = 1;
while (isOver != true) {
    let continueLoop = confirm(`[${counter}] Continue the loop?`);
    isOver = continueLoop === true ? false : true;
    counter = counter + 1;
}

Simplificando:

let isOver = false;
let counter = 1;
while (!isOver) {
    isOver = !confirm(`[${counter++}] Continue the loop?`);
}

### DO WHILE

that a do ... while loop code is always executed at least once before the first condition check is done, and a plain while may never be executed at all if the initial condition is evaluated to false at the beginning of the loop.

syntax :

do {
    code block
} while(condition);


let isOver;
let counter = 1;
 
do {
    isOver = !confirm(`[${counter++}] Continue the loop?`); // counter plus 1 into the declaration.
} while (!isOver);


### FOR LOOP 

for (initialization; condition; increment) {
    block of code
}

Into the for parentheses we can find three conditions:

    loop initialization statement;
    loop condition statement;
    loop increment statement.

#### FOR loop INITIALIZATION STATEMENT

s executed only once, before the first loop iteration. Usually, it’s used to initialize (or declare and initialize) a variable that will be used as a loop counter.

#### FOR loop condition statement

is an expression that is evaluated to a Boolean before each loop iteration. If this expression is evaluated to true, the loop will execute its code.

#### FOR loop increment statement

is always executed at the end of the current loop iteration, and most of the time it’s used to increment (or decrement, depending on the need) a loop counter that is used in a condition statement. It can be also any expression, and be left empty.


e.i.

for (let i = 0; i < 10; i++) {
    console.log(i);
}

==

let i = 0;
while (i < 10) {
    console.log(i);
i++;
}

e.i.

let values = [10, 30, 50, 100];
let sum = 0;
for (let i = 0; i < 4; i++) {
    sum += values[i];
}
console.log(sum); // -> 190


== better

let values = [10, 30, 50, 100];
let sum = 0;
for (let i = 0; i < values.length; i++) {
    sum += values[i];
}
console.log(sum); // -> 190

### LOOPS AND ARRAYS

e.i.

let names = [];
let isOver = false;
while (!isOver) {
    let name = prompt("Enter another name or press cancel.");
    if (name != null) {
        names.push(name);
    } else {
        isOver = true;
    }
}
 
console.log(names.length);

for (let i = 0; i < names.length; i++){
    console.log(names[i]);
}


e.i. Reading an Array in the reverse way:


let values = [10, 30, 50, 100];
 
for (let i = 0; i < values.length; i++) {
    console.log(values[i]); // -> 10, 30, 50, 100
}
 
for (let i = values.length - 1; i > 0; i--) {
    console.log(values[i]); // -> 100, 50, 30, 10
}
 
for (let i = 0; i < values.length; i += 2) {
    console.log(values[i]); // -> 10, 50
}


### FOR OF


for (variable of array) {
    block of code
}

Base:
let values = [10, 30, 50, 100];
let sum = 0;
for (let i = 0; i < values.length; i++) {
    sum += values[i];
}
console.log(sum); // -> 190

e.i.

let values = [10, 30, 50, 100];
let sum = 0;
for (let number of values) {
    sum += number;
}
console.log(sum); // -> 190


In our example, for (let number of values) means that the number variable will contain the subsequent elements of the values array in each iteration.


e.i. 
let cities = [
    { name: "New York", population: 18.65e6 },
    { name: "Cairo", population: 18.82e6 },
    { name: "Mumbai", population: 19.32e6 },
    { name: "São Paulo", population: 20.88e6 },
    { name: "Mexico City", population: 21.34e6 },
    { name: "Shanghai", population: 23.48e6 },
    { name: "Delhi", population: 25.87e6 },
    { name: "Tokyo", population: 37.26e6 }
];
 
for (let city of cities) {
    if (city.population > 20e6) {
        console.log(`${city.name} (${city.population})`);
    }
}


### FOR IN

It iterates through all fields of the indicated object, placing the names of these fields (or keys) in the variable. In the example, we use an object containing data about a user:

e.i.

let user = {
    name: "Calvin",
    surname: "Hart",
    age: 66,
    email: "CalvinMHart@teleworm.us"
};
 
for (let key in user) {
    console.log(key); // -> name, surname, age, email
};

we have an alternative solution, bracket notation. It allows you to refer to the selected object field using brackets

console.log(user.name); // -> Calvin
console.log(user[name]); // -> Calvin

So to show both datos we will do:

for (let key in user) {
    console.log(`${key} -> ${user[key]}`);
};


### BREAK AND CONTINUE STATEMENTS

In each of these contexts, whenever the JavaScript engine encounters a break statement, it exits the whole loop or switch statement, and jumps to the first statement after that loop or switch.

let i = 0;
// An infinite loop
while (true){
    console.log(i);
    i++;
    if (i >= 5) {
        break;
    }
}
 
alert(`Exited the loop with a break (${i}).`);


Just like break, continue can be used in loops (but not in the switch statement). When used, it applies to the closest surrounding loop. The continue statement, in contrast to break, does not end the whole loop, but rather starts the next iteration of this loop.

We can think of it as jumping right to the end of the current iteration.

for (let i = 0; i < 10; i++) {
    if (i == 3) {
        continue;
    }
    console.log(i);
}


### BREAK KEYWORD

the break keyword is present in all cases except in the default case. In contrast to if statements, switch statements do not execute just one branch, but rather they execute the entire code from the first case that matches until the end of the switch statement. 
This behavior is called pass-through and has some uses, but most of the time we want to execute only one branch, and for that reason the break keyword is present. When a JavaScript interpreter comes to a break, it will jump out of the current switch statement.

let gate = prompt("Choose gate: a, b, or c");
let win = false;
 
switch (gate) {
    case "a":
        alert("Gate A: empty");
    case "b":
        alert("Gate B: main prize");
        win = true;
    case "c":
        alert("Gate C: empty");
    default:
        alert("No gate " + String(gate));
}
 
if (win) {
    alert("Winner!");
}


Here we have to add the BREAK statement at the end of ich case if we do not want the while function to continue running the rest of the cases pieces of code.

But sometimes this behavior is exactly what we need to be done:
e.i.

let gate = prompt("Choose gate: a, b, or c");
let win = false;
 
switch (gate) {
    case "a":
    case "A":
    case 1:
    case "1":
        alert("Gate A: empty");
        break;
    case "b":
    case "B":
    case 2:
    case "2":
        alert("Gate B: main prize");
        win = true;
        break;
    case "c":
    case "C":
    case 3:
    case "3":
        alert("Gate C: empty");
        break;
    default:
        alert("No gate " + String(gate));
}
 
if (win) {
    alert("Winner!");
}

The last important part is that if a more complex code is needed inside any given case, we should place that code in separate code blocks by additionally surrounding the code with curly brackets. This will add to code readability and allow for the declaration of variables only in the given case scope.

let gate = prompt("Choose gate: a, b, or c");
let win = false;
 
switch (gate) {
    case "a": {
        let message = "Gate A";
        console.log(message);
        break;
    }
    case "b": {
        let message = "Gate B";
        console.log(message);
        break;
    }
    case "c": {
        let message = "Gate C";
        console.log(message);
        break;
    }
    default:
        alert("No gate " + String(gate));
}
 
if (win) {
    alert("Winner!");
}


### PRACTICE


let num = 100;
while (num !== 0) {
    console.log(num);
    num -= 10;
}

OR
for (let i = 100; i > 0; i -= 10 ) {
    console.log(i);
}


2.


let num1 = prompt("Ingresa el numero mayor: ", 100);
let num2 = prompt("Now the lower numer: ", 0);

for (let i = num1; i > num2; i -= 10 ) {
    console.log(i);
}

console.log('Bigger number:  ${num1}');

.3-
Exercise 3: There are ten different numbers in the following numbers array:

let numbers = [21, 45, 100, 12, 11, 78, 61, 4, 39, 22];

Write a program that first writes out all these numbers on the console, then only those that are even (hint: the remainder of dividing an even number by 2 is equal to 0), then only those that are larger than 10 and at the same time smaller than 60.


let numbers = [21, 45, 100, 12, 11, 78, 61, 4, 39, 22];
let numbersEvens = [];
let numbersSelected = [];

//Reading through the 'numbers' array, and made three actions: - showing of to the console
//... -Adding the value that in even to other object, -Adding to a object if its much to a conditional statement.

for (let key in numbers) {
    console.log(numbers[key]);
    if (numbers[key] / 2 === 0) {
        numbersEvens.push(numbers[key]);
    }
    if (numbers[key] > 10 && numbers[key] < 60) {
        numbersSelected.push(numbers[key]);
    }
}


//Showing the EVENS object
console.log("--EVENS--");
for (let key in numbersEvens) {
    console.log(numbersEvens[key]);
}

//Showing the 'SELECTED' object
console.log('--SELECTED--');
for (let key in numbersSelected) {
    console.log(numbersSelected[key]);
}


//WE can use another way of FOR, and it is simpler:

let numbers = [21, 45, 100, 12, 11, 78, 61, 4, 39, 22];

for (number of numbers) {
    console.log(number)
}

console.log("--EVENS--");
for (number of numbers) {
    if (number % 2 === 0) {
        console.log(number)
    }
}

console.log('--SELECTED--');
for (number of numbers) {
    if (number > 10 && number < 60) {
        console.log(number)
    }
}

Exercise 4: Write a program using a loop that will ask the user for the name of the movie (first prompt) and its rating from www.imdb.com (second prompt). The program will allow you to enter as many movies as you want into the movies array. Each element of the array will be an object, consisting of two fields: title and imdb. The input is completed if the user presses Cancel in the prompt dialog. Then the program should first print out to the console all movies that have a rating of less than 7, then those whose rating is greater than or equal to 7. Write the name of the movie and its rating next to each other, e.g.:


simple solution:

let movies = [];
while (true) {
    let title = prompt("Enter movie title");
    let rating = prompt("Enter movie rating (imdb)");

    if (title === null || rating === null) {
        break
    } else {
        movies.push({
            title: title,
            rating: Number(rating)
        });
    }
}

console.log("All with ratings under 7:");
for (movie of movies) {
    if (movie.rating < 7) {
        console.log(`${movie.title} (${movie.rating})`);
    }
}

console.log("All with ratings over 7:");
for (movie of movies) {
    if (movie.rating >= 7) {
        console.log(`${movie.title} (${movie.rating})`);
        break;
    }
}


Exercise 5: The contents of the object describing the position of the vessel named "Mareno" are written on the console:

LATITUDE -> 40.07288 
LONGITUDE -> 154.48535 
COURSE -> 285.6 
SPEED -> 14.0 
IMO -> 9175717 
NAME -> MARENO

The code presented below is used for this. Complete the program by declaring the missing object in place of the three dots:

let vessel = ... 
 
for( let key in vessel) { 
    console.log(`${key} -> ${vessel[key]}`); 
}

solution:

let vessel = {
    LATITUDE: 40.07288, 
    LONGITUDE: 154.48535, 
    COURSE: 285.6, 
    SPEED: 14.0, 
    IMO: 9175717, 
    NAME: 'MARENO', 
};
 
for( let key in vessel) { 
    console.log(`${key} -> ${vessel[key]}`); 
}



Exercise 6: Modify the calculator program that you made in Module 4 Section 2 in such a way that it will work in the loop until the user inputs Q in any of the prompt boxes.

while (true) {
    let firstNumber = prompt("Enter first number");
    let secondNumber = prompt("Enter second number");
    let operand = prompt("Enter operand (+, -, * or /)");
    let result;

    if (firstNumber === "Q" || secondNumber === "Q" || operand === "Q") {
        break;
    }

    firstNumber = Number(firstNumber);
    secondNumber = Number(secondNumber);

    if (!Number.isNaN(firstNumber) && !Number.isNaN(secondNumber)) {
        switch (operand) {
            case "+":
                result = firstNumber + secondNumber;
                break;
            case "-":
                result = firstNumber - secondNumber;
                break;
            case "*":
                result = firstNumber * secondNumber;
                break;
            case "/":
                result = firstNumber / secondNumber;
                break;
            default:
                result = "Error: unknown operand";
        }
    } else {
        result = "Error: at least one of the entered values is not a number";
    }
    alert(result);
}



FINAL


We can improve our contact list program a bit by using loops. You can now try to display not only the first or last contact, but all contacts in the list, regardless of their number.

Additionally, try to enclose the whole program in a loop so that the user is repeatedly asked what they want to do. The user can choose to:

display the first contact (first)
display the last contact (last)
display all contacts (all)
add a new contact (new)
exit the program (quit)
After executing the selected action, the program will give the opportunity to choose again. The program should end the actions only after the user gives a specified command, for example quit.

let choice;
let contacts = [{
name: "Maxwell Wright",
phone: "(0191) 719 6495",
email: "Curabitur.egestas.nunc@nonummyac.co.uk"
}, {
name: "Raja Villarreal",
phone: "0866 398 2895",
email: "posuere.vulputate@sed.com"
}, {
name: "Helen Richards",
phone: "0800 1111",
email: "libero@convallis.edu"
}];

while (true) {
    let oldLenght = contacts.length - 1;

    choice = prompt("What you want to do: 'quit', first', 'last', 'all', or add a 'new' contact", "new");
    
    if (choice === 'quit') {
        break;
    }

    switch (choice) {
            case "first": 
                alert("first contact data: " + contacts[0].name + " " + contacts[0].phone + " " +  contacts[0].email);
                break;
            case "last":
                alert("last contact data: " + contacts[oldLenght].name + " " + contacts[oldLenght].phone + " " + contacts[oldLenght].email);
                break;
            case "all":
                for (contact of contacts) {
                    
                    console.log(`${contact.name}  ${contact.phone}  ${contact.email}`);
                }
                alert('The list has been deployed.');
                break;
            case "new":
                let newName = prompt("Whats your name: ", "Juan");
                let newPhone = prompt("Whats your phone: ", 10000);
                let newEmail = prompt("Whats your email: ", "juan@jjj.com");
    
                if (newName === null || newPhone === null || newEmail === null) {
                    Alert("All camps must be filled!");
                    
                } else {
                    let newContact = { 
                    name: newName,
                    phone: newPhone,
                    email: newEmail 
                    };
                    contacts.push(newContact);
                    alert("The new contact was stored!");
                
                }
                break; //Modificado ultima version a testear
                
            default: alert("Not a valid operation : " + String(operation));
        }
}


# FUNTIONS

 It's a separated piece of code, constituting a certain closed logical whole, intended to perform a specific task

 The declaration and calling of functions are independent of each other

 Such modularity increases the readability of the code – it is easier to write and analyze a long program that is not a sequence of single instructions

## FUNCTIONS

function functionName() {
code
}


veamos un ejemplo comparativo:

let temperatures;
let sum;
let meanTemp;
 
temperatures = [12, 12, 11, 11, 10, 9, 9, 10, 12, 13, 15, 18, 21, 24, 24, 23, 25, 25, 23, 21, 20, 19, 17, 16];
sum = 0;
for (let i = 0; i < temperatures.length; i++) {
     sum += temperatures[i];
}
meanTemp = sum / temperatures.length;
console.log(`mean: ${meanTemp}`); // -> mean: 16.666666666666668
 
temperatures = [17, 16, 14, 12, 10, 10, 10, 11, 13, 14, 15, 17, 22, 27, 29, 29, 27, 26, 24, 21, 19, 18, 17, 16];
sum = 0;
for (let i = 0; i < temperatures.length; i++) {
     sum += temperatures[i];
}
meanTemp = sum / temperatures.length;
console.log(`mean: ${meanTemp}`); // -> mean: 18.083333333333332


Lo podemos cambiar con la siguiente declaracion de funcion:

let temperatures;

function temperaturaMedia (temperatures) {
    let sum = 0;
    let meanTemp;
    for (let i = 0; i < temperatures.length; i++) {
     sum += temperatures[i];
    }
    meanTemp = sum / temperatures.length;
    console.log(`mean: ${meanTemp}`);
}
 
temperatures = [12, 12, 11, 11, 10, 9, 9, 10, 12, 13, 15, 18, 21, 24, 24, 23, 25, 25, 23, 21, 20, 19, 17, 16];
temperaturaMedia(temperatures);
 
temperatures = [17, 16, 14, 12, 10, 10, 10, 11, 13, 14, 15, 17, 22, 27, 29, 29, 27, 26, 24, 21, 19, 18, 17, 16];
temperaturaMedia(temperatures);




O tambien, de la siguiente manera para definir variables fuera del scoope de la funcion:

let temperatures;
let sum;
let meanTemp;
 
function getMeanTemp() {
     sum = 0;
     for (let i = 0; i < temperatures.length; i++) {
      sum += temperatures[i];
     }
     meanTemp = sum / temperatures.length; 
}
 
temperatures = [12, 12, 11, 11, 10, 9, 9, 10, 12, 13, 15, 18, 21, 24, 24, 23, 25, 25, 23, 21, 20, 19, 17, 16];
getMeanTemp();
console.log(`mean: ${meanTemp}`); // -> mean: 16.666666666666668
 
temperatures = [17, 16, 14, 12, 10, 10, 10, 11, 13, 14, 15, 17, 22, 27, 29, 29, 27, 26, 24, 21, 19, 18, 17, 16];
getMeanTemp();
console.log(`mean: ${meanTemp}`); // -> mean: 18.083333333333332


### DECLARING

function statement:

function functionName() {
   code
}

e.i. let temperatures;
let sum;
let meanTemp;
 
function getMeanTemp() {
     sum = 0;
     for (let i = 0; i < temperatures.length; i++) {
         sum += temperatures[i];
     }
     meanTemp = sum / temperatures.length;    
}


### CALLING a function

e.i.

temperatures = [17, 16, 14, 12, 10, 10, 10, 11, 13, 14, 15, 17, 22, 27, 29, 29, 27, 26, 24, 21, 19, 18, 17, 16];
getMeanTemp();
console.log(`mean: ${meanTemp}`); // -> mean: 18.083333333333332


The position of the FUNCTION decleration do not matter, the program can usit when is call.

let name = 'Alice';
 
showName(); // -> Alice
 
 
function showName() {
     console.log(name);
}


### LOCAL VARIABLES

This is how we call the variables that are declared and used in some limited scope and are not visible in the whole program, which means that we can only use them inside that particular scope.

Variables declared with the let keyword are local inside the code block (i.e. inside the range limited by curly brackets {}), while variables declared with the var keyword are local inside the function block. So if you declare a variable inside a function block, whether using let or var, it will only be visible (and usable) inside the function block. This is very useful, because usually the variables you use inside a function are not needed outside of it.

In general, we should strive to keep the function code as separate from the surrounding context as possible, among other things by not using global variables inside it


### RETURN STATEMENT

What exactly is return for?

    First, it causes the function to end exactly where this word occurs, even if there are further instructions.

    Second, it allows us to return a given value from inside the function to the place where it was called.

function showMsg() {
     console.log("message 1");
     return;
     console.log("message 2");
}
showMsg(); // -> message 1


If we place some expression (literal, variable, function call) immediately after the return keyword, the value of this expression will be returned by the completed function to the place where it was called


function getTrue() {
     return true;
}
let test = getTrue();
console.log(test); // -> true



e.i.

let temperatures;
let meanTemp;
 
function getMeanTemp() {
     let sum = 0;
     let result;
     for (let i = 0; i < temperatures.length; i++) {
      sum += temperatures[i];
     }
     result = sum / temperatures.length;
     return result;  
}
 
temperatures = [12, 12, 11, 11, 10, 9, 9, 10, 12, 13, 15, 18, 21, 24, 24, 23, 25, 25, 23, 21, 20, 19, 17, 16];
meanTemp = getMeanTemp();
console.log(`mean: ${meanTemp}`);
 

==

function getMeanTemp() {
     let sum = 0;
     for (let i = 0; i < temperatures.length; i++) {
         sum += temperatures[i];
     }
     return sum / temperatures.length;
}

==

let temperatures;
function getMeanTemp() {
     let sum = 0;
     for (let i = 0; i < temperatures.length; i++) {
      sum += temperatures[i];
     }
     return sum / temperatures.length;
}
temperatures = [12, 12, 11, 11, 10, 9, 9, 10, 12, 13, 15, 18, 21, 24, 24, 23, 25, 25, 23, 21, 20, 19, 17, 16];
console.log(`mean: ${getMeanTemp()}`);


Our getMeanTemp is slowly beginning to look like a normal function. It is a logically independent piece of code, it returns a calculated value, and it operates on local variables. There is one small problem left to solve. We count the mean using the data contained in the global variable temperatures. And the function should be independent of what is happening outside it. At the same time, it should allow us to calculate the mean value for different data. How do we reconcile these two conflicting demands?

### PARAMETERS

The use of parameters in functions is optional.

Each parameter inside a function will be treated as a local variable. A function whose definition specifies the parameters must be invoked in an appropriate way. When such a function is called, the values (literals, variables, function calls) should be placed in parentheses after its name, and are treated as parameters inside the function. The values given during a call are called arguments. Arguments, if there is more than one, are separated by commas and must be passed in the same order as the parameters we define in the function declaration.

function add(first, second) {
return first + second;
}
 ==

let result = add(5, 7));
console.log(result); // -> 12


e.i.
function getElement(elements, index) {
return elements[index];
}


let names = ["Alice", "Bob", "Eve", "John"];
let name = getElement(names, 2);
console.log(name); // -> Eve



e.i.

function getMeanTemp(temperatures) {
     let sum = 0;
     for (let i = 0; i < temperatures.length; i++) {
      sum += temperatures[i];
     }
     return sum / temperatures.length;
}
 
let day1 = [12, 12, 11, 11, 10, 9, 9, 10, 12, 13, 15, 18, 21, 24, 24, 23, 25, 25, 23, 21, 20, 19, 17, 16];
console.log(`mean: ${getMeanTemp(day1)}`); // -> mean:
16.666666666666668
 
let day2 = [17, 16, 14, 12, 10, 10, 10, 11, 13, 14, 15, 17, 22, 27, 29, 29, 27, 26, 24, 21, 19, 18, 17, 16];
console.log(`mean: ${getMeanTemp(day2)}`); // -> mean:
18.083333333333332


The first time the getMeanTemp function is called, the day1 variable is passed on to the getMeanTemp function as an argument. The calculations performed inside the function using the temperatures parameter will therefore be based on the values from the day1 variable. In the second call, we pass another array to the function, stored in the day2 variable.

You can probably already point out one more thing: when calling the console.log method (a function related to the console object) we also pass an argument to it – a string to be displayed on the console. This means that we have been using the parameters of the function since the beginning of the course.

### SHADOWING

he add function has two parameters: first and second. At the same time, we will declare, out of the function, global variables named first, second, third, and fourth.

If inside the function, we refer to the variable:

first, it will be treated as the parameter with such a name that shadows the first global variable (i.e. we will operate on the value passed as the first argument)
second, it will also be treated as the function parameter (the value passed as the second argument)
third, it will be treated as a global variable, because inside the function there is neither a local variable nor a parameter with that name that would shadow it;
fourth, it will be treated as global, the same as third.

function add(first, second) {
return first + second;
}
 
let first = 10, second = 20, third = 40, fourth = 80;
console.log(add(first, second)); // -> 30
console.log(add(second, third)); // -> 60
console.log(add(third, fourth)); // -> 120

e.i.
let a = 100, b = 200, c = 300;
 
function test(a) {
     let b = 10;
     console.log(a); // parameter a
     console.log(b); // local variable b
     console.log(c); // global variable c
}
 
test(1);   // -> 1
      // -> 10
      // -> 300
 
console.log(a); // -> 100
console.log(b); // -> 200
console.log(c); // -> 300


## FUNCTIONS 2.
### PARAMETERS VALIDATIONS

Let's go back to the example with the getMeanTemp function. The last version we wrote needs an array of numbers as an argument. Before starting the calculation, we can check if the value passed to it is actually an array.

function getMeanTemp(temperatures) {
     if (!(temperatures instanceof Array)) {
      return NaN;
     }
     let sum = 0;
     for (let i = 0; i < temperatures.length; i++) {
      sum += temperatures[i];
     }
     return sum / temperatures.length;
}

console.log(getMeanTemp(10)); // -> NaN
console.log(getMeanTemp([10, 30])); // -> 20


### RECURSION

During your math lessons, you probably came across the concept of factorials. A factorial is a function, indicated by an exclamation mark in mathematical notation. We pass an integer to this function and its result is obtained by multiplying all integers from the number 1 to the number given as an argument. Formally, you define a factorial as follows:

n!=n∙(n-1)∙(n-2)∙... ∙2∙1

So, for example, the factorial of 6 is:

6!=6∙5∙4∙3 ∙2∙1=720

Let's try to write a function that will calculate the factorial from the given number.

It will take the parameter n and return the calculated value.


e.i.
function factorial (n) {
     let result = 1;
     while (n > 1) {
         result *= n;
         n--;
     }
     return result;
}
 
console.log(factorial(6)); // -> 720


However, the definition of a factorial can be written in a slightly different way. It will be the factorial of the previous element n - 1 multiplied by n.

For example, 6! is 5! multiplied by 6. Such a factorial definition uses the recursion, i.e. referring a function to itself (but with a different argument). A recursion is a mechanism that allows to simplify the formal notation of many mathematical functions and present them in an elegant form. We can also successfully use recursion in programming.

==

function factorial (n) {
     return n > 1 ? n * factorial(n - 1) : 1;
}
 
console.log(factorial(6)); // -> 720

![alt text](image.png)
https://skillsforall.com/content/jse1/1.0/m5/course/en-US/assets/6c2ac95dde1fb99202fc7b7a4612adb3e46873a0.png


### FUNCTIONS AS FIRST CLASS MEMBERS

This term means that functions can be treated as any data, which can be stored in variables or passed as arguments to other functions. For example, we can declare the showMessage function and then store it in the variable sm.

function showMessage(message) {
     console.log(`Message: ${message}`);
}
 
let sm = showMessage;

sm("This works!"); // -> Message: This works!
console.log(typeof sm); // -> function


Notad la diferencia entre llamar la funcion y asignarla:

function doNothing() {
     return undefined;
}
 
let a = doNothing(); // assign result of function call
let b = doNothing;   // assign a function
 
console.log(typeof a); // -> undefined
console.log(typeof b); // -> function


e.i.

function add(a, b) {
     return a + b;
}
 
function multiply(a, b) {
     return a * b;
}
 
function operation(func, first, second) {
     return func(first, second);
}
 
console.log(operation(add, 10, 20)); // -> 30
console.log(operation(multiply, 10, 20)); // -> 200


### FUNCTIONS EXPRESSIONS

To store a function in a variable or pass it as an argument to call a function, you do not necessarily have to declare it previously and use its name.

Let's go back to our example with the add function:

function add(a, b) {
     return a + b;
}
 
let myAdd = add;
console.log(myAdd(10, 20)); 	// -> 30
console.log(add(10, 20));	// -> 30

==

let myAdd = function add(a, b) {
     return a + b;
}
 
console.log(myAdd(10, 20)); // -> 30
console.log(add(10, 20)); // -> 30


In the example, we again declare the add function, and at the same time store it in the myAdd variable.

This form of defining a function is called function expression.

simply remove the name following the function keyword to change the function from named to anonymous.


let myAdd = function(a, b) {
     return a + b;
}
console.log(myAdd(10, 20)); // -> 30


e.i.

function operation(func, first, second) {
     return func(first, second);
}
 
let myAdd = function(a, b) {
     return a + b;
}
 
console.log(operation(myAdd, 10, 20)); // -> 30
 
console.log(operation(function(a, b) {
     return a * b;
}, 10, 20)); // -> 200


The result is a multiplication, although the name of the new function (or the variable in which it could be placed) will not appear anywhere. The function has been defined only to pass it once into the operation function. 

### CALLBACKS

Functions that are passed as arguments to other functions may seem quite exotic and not very helpful, but in fact, they are a very important part of programming. So important that they even get their own name. They are callback functions. As we have seen in previous examples, a function that receives a callback as an argument can call it at any time. Importantly, in our examples, the callback is run synchronously, that is, it is executed in a strictly defined order resulting from where it is placed among the other instructions.

### Synchronous callbacks 

Subsequent instructions are executed in the order in which they are placed in the code. If you call a function, the instructions in it will be executed at the time of the call. If we pass another function to this function as an argument, and we call it inside an outer function as well, then all instructions will keep their natural order.

e.i.
let inner = function() {
     console.log('inner 1');
}
 
let outer = function(callback) {
     console.log('outer 1');
     callback();
     console.log('outer 2');
}
 
console.log('test 1');
outer(inner);
console.log('test 2');

OUTPUT:
test 1
outer 1
inner 1
outer 2
test 2


### ASTNCHRONOUS CALLBACKS

Asynchronous operation of programs is a rather complex topic, strongly dependent on a particular programming language, and often also on the environment.

In the case of client-side JavaScript running in a browser, it is limited to event-based programming, i.e. the asynchronous response to certain events. An event can be a signal sent by a timer, a user action (e.g. pressing a key or clicking on a selected interface element), or information about receiving data from the server.

Using appropriate functions, we combine a specific type of event with a selected callback function, which will be called when the event occurs.

E.I.

One of the simplest cases when there is an asynchronous execution of instructions is the use of the setTimeout function. This function takes another function (a callback) and the time expressed in milliseconds as arguments. The callback function is executed after the specified time, and meanwhile, the next program instruction (placed in the code after setTimeout) will be executed.

Thus, the moment the callback function is called is not determined by its order, but by an arbitrarily imposed delay. The delay only applies to the callback function given to setTimeout, while the rest of the code is still executed synchronously.

Let's modify the previous example a bit. In the outer function, we do not call callback() immediately, but pass it to setTimeout, which executes it with a delay of 1000 milliseconds (one second).

E.I. 
let inner = function() {
console.log('inner 1');
}
 
let outer = function(callback) {
console.log('outer 1');
let timerId = setInterval(callback, 1000) /*ms*/;
console.log('outer 2');
 
setTimeout(function(){
     clearInterval(timerId);
}, 5500);
}
 
console.log('test 1');
outer(inner);
console.log('test 2');


OUTPUT:

outer 1
outer 2
test 2
...
inner 1
inner 1
inner 1
inner 1
inner 1


### SETTIMEOUT AND SETINTERVAL FUNCTIONS


If we run the JavaScript code on the client side, in the browser, it is always associated with the website. The window in which this page is located is represented in the client-side JavaScript by a global window variable.

The window object has a method (or its own function) named addEventListener. This function allows you to register a certain action to be performed in response to a window-related event.

Such an event can be a "click", which is a single mouse click on any place on the page (there is a limited set of named events associated with a particular object, to which it can react).

The action to be taken is passed to the addEventListener method as a callback function.

window.addEventListener("click", function() {
     console.log("clicked!");
});




### ARROW FUNCTION

An arrow function is a shorter form of a function expression. An arrow function expression is composed of: parentheses containing zero to multiple parameters (if exactly one parameter is present, the parentheses can be omitted); an arrow that looks like this "=>"; and the body of the function, which can be surrounded by curly brackets if the body is longer. If an arrow function has only one statement and returns its value, we can omit the return keyword, as it will be implicitly added.

let add = function(a, b) {
     return a + b;
}
console.log(add(10, 20)); // -> 30

==

let add = (a, b) => {
     return a + b;
}
console.log(add(10, 20)); // -> 30

==

let add = (a, b) => {
     return a + b;
}
console.log(add(10, 20)); // -> 30


If the arrow function takes exactly one parameter, the parentheses may be omitted. Let's go back to the examples with the recursive factorial function, which takes exactly one parameter, n. In the previous example, we declared it using the function statement:

function factorial(n) {
     return n > 1 ? n * factorial(n - 1) : 1;
}
console.log(factorial(5)); // -> 120

==

Using the arrow function expression, we can write it in an even more compact form. Note that this time, the parameter is not given in parentheses (again,– if the arrow function takes exactly one parameter, the parentheses can be omitted). Since the function returns the result of exactly one statement, the return keyword can also be omitted.


E.I.
One typical example of using arrow functions is the forEach method, available in Array type data. We have learned several ways of passing through array elements, using different types of loops. The forEach method is another, and frankly speaking, currently the most used one. This method takes as an argument ... a function.

let names = ['Alice', 'Eve', 'John'];
function showName(element) {
     console.log(element);
}
names.forEach(showName); // -> Alice, Eve, John

## PRACTICE

Exercise 1: Arrays in JavaScript have a sort method available which, as you might guess, allows you to sort its elements. This method takes as an argument a function that will compare two elements of the array. The function should return zero if we consider the arguments to be the same, a value less than zero if we consider the first one to be smaller than the second, and a value larger than zero otherwise. Take a look at the example:


let numbers = [50, 10, 40, 30, 20];
function compareNumbers(a, b) {
     let retVal = 0;
     if (a < b) {
      retVal = -1;
     } else if(a > b) {
      retVal = 1;
     }
     return retVal;
}
let sorted = numbers.sort(compareNumbers);
console.log(sorted); // [10, 20, 30, 40, 50]

Task 1A. Try to modify the above piece of code to make it as short as possible. Suggestions:

use an anonymous function;
use an arrow function;
consider skipping the if statement.

e.i.

let numbers = [50, 10, 40, 30, 20];
function compareNumbers(a, b) {
     let retVal = a < b ? -1 : 1; 
     return retVal;
}

let sorted = numbers.sort(compareNumbers);
console.log(sorted); // [10, 20, 30, 40, 50]


==

//use an anonymous function;
//use an arrow function;
//consider skipping the if statement.
let numbers = [50, 10, 40, 30, 20];

let sorted = numbers.sort(function(a, b) {
    let retVal = 0;
    retVal = a > b ? 1 : -1;
    return retVal
    }); // asignamos a sorted el resultado 
//de la funcion llamada sort,

console.log(sorted); // [10, 20, 30, 40, 50]


REAL SOLUTION:


let numbers = [50, 10, 40, 30, 20];
let sorted = numbers.sort((a, b) => a - b);
console.log(sorted); // [10, 20, 30, 40, 50]


REVERSED:;


let numbers = [50, 10, 40, 30, 20];
let sorted = numbers.sort((a, b) => b - a); //& here the diference
console.log(sorted); // [10, 20, 30, 40, 50]


Exercise 2: Write three functions with the names add, sub, and mult, which will take two numerical arguments. The functions are to check if the given arguments are integers (use Number.isInteger). If not, they return NaN, otherwise they return the result of addition, subtraction, or multiplication respectively. The functions are to be declared using a function statement.

Example of use and expected results:


function add(a, b){ 
    if (Number.isInteger(a) && Number.isInteger(b)){
        return a + b; 
    } else {
        return NaN;
    }
}
function sub(a, b){ 
    if (Number.isInteger(a) && Number.isInteger(b)){
        return a - b; 
    } else {
        return NaN;
    }
}
function mult(a, b){ 
    if (Number.isInteger(a) && Number.isInteger(b)){
        return a * b; 
    } else {
        return NaN;
    }
}

console.log(add(12, 10)); // -> 22
console.log(mult(12, 10.1)); // -> NaN


Exercise 3: Rewrite the functions from the previous task using an arrow function expression, trying to write them in the shortest possible form.

Example of use and expected results:

let add = (a, b) => {
    return Number.isInteger(a,b) ? a + b: NaN;
};

let sub = (a, b) => {
    return Number.isInteger(a,b) ? a - b: NaN;
};

let mult = (a, b) => {
    return Number.isInteger(a,b) ? a * b: NaN;
}

console.log(add(12, 10)); // -> 22
console.log(sub(12, 10)); // -> 2
console.log(mult(10, 10.1)) // -> NaN


||

let add = (a, b) => !Number.isInteger(a) || !Number.isInteger(b) ? NaN : a + b;
let sub = (a, b) => !Number.isInteger(a) || !Number.isInteger(b) ? NaN : a - b;
let mult = (a, b) => !Number.isInteger(a) || !Number.isInteger(b) ? NaN : a * b;

/*Exercise 4: Write an action function that will take the callback function as 
its first argument and the other two arguments as numbers. As a callback
function, you will be able to pass one of the three functions from the 
previous task. The action function will call the callback function passed 
to it and will return the obtained result. The callback function will accept
the second and third arguments from the action call.
Example of use and expected results:*/

function action(callback, a, b) {
    return callback(a,b);
}



### PRACTICE contacts list

let contacts = [{
    name: "Maxwell Wright",
    phone: "(0191) 719 6495",
    email: "Curabitur.egestas.nunc@nonummyac.co.uk"
}, {
    name: "Raja Villarreal",
    phone: "0866 398 2895",
    email: "posuere.vulputate@sed.com"
}, {
    name: "Helen Richards",
    phone: "0800 1111",
    email: "libero@convallis.edu"
}];


let choice;

function showContact(contacts, index){
    let searched = prompt('Cual es el nombre del contacto buscado: ', 'Raja Villarreal');
    for (let contact of contacts) {
        if (contact.name === searched){
            console.log(`${contact.name}  ${contact.phone}  ${contact.email}`);
        } else {
            console.log(`The contact name has no been found in CONTACTS DB`);
        }
}}

function showContact0(contacts, index){
    return alert("first contact data: " + contacts[index].name + " " + contacts[index].phone + " " +  contacts[index].email);
}

function showAllContacts(contacts){
    for (contact of contacts) {
        console.log(`${contact.name}  ${contact.phone}  ${contact.email}`);
    }
    alert('The list has been deployed.');
}

function addNewContact(contacts, name, phone, number) {
    let newContact = { 
                    name: name,
                    phone: phone,
                    email: number 
                    };
    contacts.push(newContact);
    alert("The new contact was stored!");
}

while (true) {
    choice = prompt("What you want to do: 'quit', first', 'last', 'all', 'search' for contact, or add a 'new' contact", "new");
    
    if (choice === 'quit') {
        break;
    }

    switch (choice) {
            case "first": 
                showContact0(contacts, 0);
                break;
            case "last":
                let oldLenght = contacts.length - 1;
                showContact0(contacts, oldLenght);
                break;
            case "all":
                showAllContacts();
                break;
            case 'search':
                showContact();
                break;
            case "new":
                let newName = prompt("Whats your name: ", "Juan");
                let newPhone = prompt("Whats your phone: ", 10000);
                let newEmail = prompt("Whats your email: ", "juan@jjj.com");
    
                if (newName === null || newPhone === null || newEmail === null) {
                    Alert("All camps must be filled!");
                    
                } else {
                    addNewContact(contacts, newName, newPhone, newEmail)
                }
                break; //Modificado ultima version a testear
                
            default: alert("Not a valid operation : " + String(operation));
        }
}






lookiung options, in proicess

let contacts = [{
    name: "Maxwell Wright",
    phone: "(0191) 719 6495",
    email: "Curabitur.egestas.nunc@nonummyac.co.uk"
}, {
    name: "Raja Villarreal",
    phone: "0866 398 2895",
    email: "posuere.vulputate@sed.com"
}, {
    name: "Helen Richards",
    phone: "0800 1111",
    email: "libero@convallis.edu"
}];


let choice;

function showContact(contacts, index){
    return alert("Required contact data: " + contacts[index].name + " " + contacts[index].phone + " " +  contacts[index].email);
  
    
}

function showAllContacts(contacts){
    for (contact of contacts) {
        console.log(`${contact.name}  ${contact.phone}  ${contact.email}`);
    }
    alert('The list has been deployed.');
}

function addNewContact(contacts, name, phone, number) {
    let newContact = { 
                    name: name,
                    phone: phone,
                    email: number 
                    };
    contacts.push(newContact);
    alert("The new contact was stored!");
}

while (true) {
    choice = prompt("What you want to do: 'quit', first', 'last', 'all', 'search' for contact, or add a 'new' contact", "new");
    
    if (choice === 'quit') {
        break;
    }

    switch (choice) {
            case "first": 
                showContact(contacts, 0);
                break;
            case "last":
                let oldLenght = contacts.length - 1;
                showContact(contacts, oldLenght);
                break;
            case "all":
                showAllContacts(contacts);
                break;
            case 'search':
                let searched = prompt('Cual es el nombre del contacto buscado?', 'Maxwell Wright');
                let index = -1;
                let index0;
                for (let contact of contacts) {
                    index += 1;
                    if (contact.name === searched){
                        index0 = index;
                    }
                }
                showContact(contacts, index0);
                break;
            case "new":
                let newName = prompt("Whats your name: ", "Juan");
                let newPhone = prompt("Whats your phone: ", 10000);
                let newEmail = prompt("Whats your email: ", "juan@jjj.com");
    
                if (newName === null || newPhone === null || newEmail === null) {
                    Alert("All camps must be filled!");
                    
                } else {
                    addNewContact(contacts, newName, newPhone, newEmail)
                }
                break; //Modificado ultima version a testear
                
            default: alert("Not a valid operation : " + String(operation));
        }
}

2.


Objectives
Familiarize the student with:

Function basics (what are functions, declaring functions, calling functions, local variables, the return statement, function parameters, shadowing);
Functions as first-class members (function expressions, passing a function as a parameter, callbacks);
Arrow functions (declaring and calling);
Recursion (basic idea).
Scenario
We will use the functions to add one more item of functionality. Arrays have a sort method that allows us to sort their elements. To this method, we pass a function which should compare two elements of the array and decide which one is smaller and which one is bigger. If the first element is smaller, the function returns a value less than zero, if they are equal it returns zero, and if the first is larger, it returns a value greater than zero. For example, the array:


let numbers = [10, 50, 40, 20];
can be sorted in ascending order with a call:


numbers.sort(function (a, b) {
     let retVal = 0;
     if (a > b) {
      retVal = 1;
     } else {
      retVal = -1;
     }
     return retVal;
});

or more simply:

numbers.sort((a, b) => a - b);

Give the user the option to select a sort action from the list. When this option is selected, the user should be able to specify whether they want to sort the contacts by name, phone, or email.

__

Given function solutions

--

let showContact = function(contacts, i) {
    if (contacts instanceof Array && contacts[i]) {
        console.log(`${contacts[i].name} / ${contacts[i].phone} / ${contacts[i].email}`);
    }
}

let showAllContacts = function(contacts) {
    if (contacts instanceof Array) {
        for (contact of contacts) {
            console.log(`${contact.name} / ${contact.phone} / ${contact.email}`);
        }
    }
}

let addNewContact = function(contacts, name, phone, email) {
    if (contacts instanceof Array && name && phone && email) {
        contacts.push({
            name: name,
            phone: phone,
            email: email
        });
    }
}

function sortContacts(contacts, sortBy) {
    return contacts.sort((a, b) => {
        // Comparador basado en el campo especificado (name, phone o email)
        if (a[sortBy] < b[sortBy]) {
            return -1;
        } else if (a[sortBy] > b[sortBy]) {
            return 1;
        } else {
            return 0;
        }
    });
}

let sortedBy = prompt('How do you want to sorted: ', 'name');
sortContacts(contacts, sortedBy);
showAllContacts(contacts);



# ERRORS, EXCEPTIONS, DEBUGGING AND TROUBLESHOOTING 
Errors in the operation of programs happen. We have to accept that, while trying to minimize their number and mitigate the damage they can potentially cause.
Edsger W. Dijkstra: "If debugging is the process of removing software bugs, then programming must be the process of putting them in".

### Natural languages and communication errors 
programming languages are used to precisely formulate unambiguously interpretable sentences (instructions). And just like natural languages, they have their grammar and vocabulary.

    SINTAX rules 
    - (Falta de un ;) The interpreter (e.g. the JavaScript engine) or compiler cannot guess the meaning of what we have written. If such an error occurs, it will require us to correct it.

    REFERENCE ERROR 
    - (Una funcion que es escrita mal al llamarla) Semantic error.

    LOGICAL ERRORS 
    - A logical error makes it possible to execute the instruction, but it will give the wrong result. An instruction with a semantic error will make no sense, so most likely it will not be possible to execute it at all in this form.

### Errors and exceptions in JavaScript

try {
    console.log('abc'); // -> abc
    conole.log('abc');
} catch (error) {  
    console.log(error.message); // -> conole is not defined 
}

### Errors without exceptions

e.i. Arithmetic errors:
console.log(100 / 0); // -> Infinity
console.log(100 * "2"); // -> 200
console.log(100 * "abc"); // -> NaN

e.i. 
console.log(Math.pow("abc", "def")); // -> NaN

This time, we use the pow method of Math, which is used to raise a given number to the given power.

The conclusion is quite simple – if you are learning about a new function or operator, you have to check in the documentation (e.g. on the MDN page) how they behave in the case of errors. Some of them will generate exceptions, while others will return some specific values. Depending on that, you will be able to properly prepare yourself for handling errors using the try method or simple conditional instructions. By the way, for the examples just shown, the most sensible solution would be to check if the provided values really are numbers (remember the typeof operator?).

### Limited confidence
Programs are not run in a vacuum. Usually during their execution, there are interactions with users (e.g. entering data needed to calculate certain values) or other programs or systems (e.g. downloading data from the server). The behavior of both users and other systems should be treated with caution, and we cannot assume that the user will provide data in the format we require, or that the data server will always work. 
If, for example, we write a calculator to which the user enters their values, then we should probably check if the divisor is not a zero before we do the division. Theoretically, the user should know that we do not divide by zero, but we are responsible for the stability of the program. Do not believe the user or other systems. Predict what may go wrong, and check the data received before you use it in your program.

e.i. 
let sX = prompt("Enter the first number");
let sY = prompt("Enter the second number");
let x = Number(sX);
let y = Number(sY);
if (Number.isFinite(x) && Number.isFinite(y) && y !== 0) {
    console.log(x / y);
} else {
    console.log("incorrect arguments");
}

### More JavaScript errors and exceptions
SyntaxError
As we previously said, a SyntaxError appears when a code is ill-formed, when there are typos in the keywords, unmatching parentheses or brackets, etc. The code can’t even be executed,

ReferenceError
It occurs when we try to access a function or a variable that doesn't exist. The JavaScript engine does not know the meaning of the given name, so it is an error that we will classify as a semantic error.

TypeError
This type of error occurs when a certain value is not of the expected type (i.e. you try to perform an operation on it that is not acceptable). his is a typical run-time error, so the appropriate exception will be thrown while the program is running, after reaching the problematic instruction.

RangeError
is generated when you pass a value to a function that is outside its acceptable range.
Is a run-time error.

Other errors - 
EvalError, InternalError, and URIError, but they’re rather rare, and we’ll come back to them if needed.

### The try...catch statement
 exceptions interrupt the program execution. The try...catch construction, which we also mentioned before, allows you to change this default action. The program will interrupt what it is currently doing, but it will not terminate automatically. The syntax for try...catch looks like this:
 try {
    // code to try
} catch (error) {
    // code to run in case of an error, which throw an exception
}

e.i.
try {
    let a = b;
} catch (error) {
    console.log("Caught " + error); // -> Caught ReferenceError: b is not defined
}
console.log("We handled the exception!"); // -> we handled the exception!

### conditional exception handling
Sometimes we want to be able to react differently to specific types of errors inside the catch block. We can do this by using the operator instanceof. We’ll discuss the operator itself further down the road, because it’s a rather complicated topic. For now, it’s enough to know how we can use it when handling errors.

The syntax for the instanceof operator looks like this:


variable instanceof type

e.i.
let result = error instanceof ReferenceError;

// The operator instanceof returns a boolean, so this expression will return true if the error variable does indeed hold a type ReferenceError

let a = -2;
try {
    a = b;
} catch (error) {
    if (error instanceof ReferenceError) {
        console.log("Reference error, reset a to -2"); // -> Reference error, reset a to -2
        a = -2;
    } else {
        console.log("Other error - " + error);
    }
}
console.log(a); // -> -2

### The finally statement
The last optional block of the try statement is the finally block. It can be used with or without the catch block, and it’s always executed after try and catch blocks, regardless of whether any errors are thrown. The syntax for try...finally looks like this:

try {
    // code to try
} finally {
    // this will be always executed
}

e.i.
let a = 10;
try {
    a = 5;
} finally {
    console.log(a); // -> 5
}
console.log(a); // -> 5

e.i.
let a = 10;
try {
    a = b;  // ReferenceError
} finally {
    console.log(a); // -> 10
}
console.log(a);

The finally block can also be used together with the catch block, as both of them are optional, but at least one of them is required by the try statement, and if none of them is present, a SyntaxError is thrown.

e.i.
let a = 10;
try {
    a = b;  // ReferenceError
} catch (error) {
    console.log("An Error!"); // -> An Error!
} finally {
    console.log("Finally!"); // -> Finally!
}
console.log(a); // -> 10

### Why should we use finally block

Try...catch...finally blocks can be nested, so we can use a whole try...catch block inside another try...catch block. This is useful when we expect multiple errors to occur and need to handle them all.

e.i.
let a = 10;
try {
    a = b; // First ReferenceError
} catch (error) {
    try {
        console.log(b); // Second ReferenceError
    } catch {
        console.log("Second catch!"); // -> Second catch!
    }
} finally {
    console.log("Finally!"); // -> Finally!
}

### The throw statement and custom errors

To throw an exception, we use the throw instruction. It is followed by any value that will be treated as an exception. It can be, for example, a number, or one of the ready-made error objects (e.g. RangeError).
console.log("start"); // -> start

try {
    throw 100;
} catch (error) {
    console.log(error); // -> 100
}
console.log("end"); // -> end

Let's try to write something a little more sensible.

e.i.
function factorial(n) {
    let result = 1;
    for (; n > 1; n--) {
        result = result * n;
    }
    return result;
}
 
console.log(factorial(3)); // -> 6
console.log(factorial(5)); // -> 120
console.log(factorial(8)); // -> 40320
console.log(factorial(20)); // -> 2432902008176640000
console.log(factorial(1000)); // -> Infinity

Let's say that we are a little scared by the large numbers returned by our function, especially the Infinity value, so we decide to limit the maximum range of supported values. We will not accept arguments larger than 20.

function factorial(n) {
    if (n > 20) {
        throw new RangeError("Max value 20");
    }
    let result = 1;
    for (; n > 1; n--) {
        result = result * n;
    }
    return result;
}
 
console.log(factorial(20)); // -> 2432902008176640000
console.log(factorial(1000)); // -> Uncaught RangeError: Max value 20

As we mentioned earlier, the throw instruction can take any value. Previously, we used a simple number, but this time we’re reaching for something more complex. It is an object, which is a composite data type. You can create a new object in many ways, including by using the operator new. Using this operator, we create a RangeError class object, which is a predefined error that we discussed a while ago. The new object is initiated by the Max value 20 string. And such a new object, of the RangeError type, containing, among other things, the string we provided, will be thrown if the n parameter exceeds the allowed value.

## PRACTICE 
Exercise 1: Write your own div function that will take two call arguments and return the result of dividing the first argument by the second. In JavaScript, the result of dividing by zero is the value Infinity (or -Infinity, if we try to divide a negative number). Change this. If you pass 0 as the second argument, your function should throw a RangeError exception with the appropriate message. Prepare a test call of the function for both valid division and division by zero.

function div(a, b) {
    if (b == 0) {
        throw new RangeError("Can't divide by 0");
    }
    return a / b;
}
console.log(div(4, 2)); // -> 2
console.log(div(4, 0)); // -> Uncaught RangeError: Can’t divide by 0

Exercise 2: The following array of numbers has been declared:


let numbers = [10, 40, 0, 20, 50];
Write a program that, in a loop, divides the number 1000 by successive elements of the numbers array, displaying the result of each division. To divide the numbers, use the function from the previous task. Use the try...catch construction to handle an exception thrown in the case of division by zero. If such an exception is caught, the program should print an appropriate message (taken from the exception) and continue its operation (division by successive elements of the array).


==


function div(a, b) {
    if (b == 0) {
        throw new RangeError("Can't divide by 0");
    }
    return a / b;
}

let numbers = [10, 40, 0, 20, 50];


for (let i = 0; i < numbers.length; i++) {
    let result;
    try {
        result = div(1000, numbers[i]);
    } catch (e) {
        result = e.message;
    }
    console.log(result);
}

### Testing and debugging your code
### Debugging 
To be conducted efficiently, debugging requires tools, and if our code is executed in the browser, we almost certainly have all the necessary tools already available.

To check if our browser supports this functionality, we can simply try to execute this code with the developer console opened.

### Step-by-step ptogram execution

So we know already that the debugger statement, when encountered by JavaScript, will stop code execution at that place. Depending on the browser we’re using, the flow control buttons can look different, and can be located in different places. In general, all modern browsers support the following options to control the execution of the script in debug mode:

Resume / Continue. This will resume the execution of the script in a normal way, and is used when we’ve checked what we wanted to check, and now we want to continue with the execution of the script.

Step Into. This executes the next instruction in the code only, and pauses it again, and we use this when we want to analyze the code in detail, or check which exact path the execution takes when complex branching is happening due to cascading if...else statements, or other complicated logic. If the next instruction is a function call, using Step Into will jump inside the code of this function.

Step Over. This works like Step Into, except that if this is used when the next instruction is a function call, the code will not jump into the function code, but the whole function will be executed, and the program will be paused again after jumping out of this function. This is often used when the next instruction is a call to a function where we don’t know if it will have any impact, or we’re simply not interested in looking.

Step Out. This allows us to immediately jump out of a function in which the code is paused.

### Preparation
 of the enviroment and an example
### Use of the debugger statement
### Resume Execution
### How to deal without the debugger statement
### Step over
### Step into
### Call stack
### Step out
## PRACTICE

[text](../../../../Downloads/JavaScript_Essentials_1_Badge20240213-29-nfg5tv.pdf)



