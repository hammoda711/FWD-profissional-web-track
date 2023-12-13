### falsy values:

- the Boolean value `false`
- the `null` type
- the `undefined` type
- the number `0`
- the empty string `""`
- the odd value `NaN` 

-----------------

### truely values:

- true

- 42

- "pizza"

- "0"

- "null"

- "undefined"

- {}

- []

------------------

**TIP:** To print out the average salary with commas (i.e. 59,124), use the `toLocaleString()` method and pass it the locale "en-US". For example, `salary.toLocaleString("en-US")`.

----------------

### note on switch statment:

+= means that print thcurrent case and the next

```js
var prize = "";

switch (winner) {
  case 1:
    prize += "a trip for two to the Bahamas and "; 
    // += means that print thcurrent case and the previous
  case 2:
    prize += "a four piece furniture set.";
    break;
  case 3:
    prize += "a smartwatch and ";
  default:
    prize += "tickets to the circus.";
}

console.log("You've won " + prize);
```

-------------------

### notes on the ternary condition

```js
var adult = true;
var preorder = true;

console.log("It costs $" + (adult ? "40.00" : "20.00") + " to attend the concert. Pick up your tickets at the " + (preorder ? "will call" : "gate") + ".");
```

-------------------------

### warning

while loop **without counter increment** is an **infinit **loop it would crash the browser

---------------------

### notes on function:

**functions** package up code so you can easily use (and reuse) a block of code. **Parameters** are variables that are used to store the data that's passed into a function for the function to use. **Arguments** are the actual data that's passed into a function when it is invoked:

---------

### notes on global scope:

- If an identifier is declared in **global scope**, it's available *everywhere*.
- If an identifier is declared in **function scope**, it's available *in the function* it was declared in (even in functions declared inside the function).
- When trying to access an identifier, the JavaScript Engine will first look in the current function. If it doesn't find anything, it will continue to the next outer function to see if it can find the identifier there. It will keep doing this until it reaches the global scope.
- Global identifiers are a bad idea. They can lead to bad variable names, conflicting variable names, and messy code.

------

### notes on hoisting:

- JavaScript hoists function declarations and variable declarations to the top of the current scope.
- Variable *assignments* are not hoisted.
- Declare functions and variables at the top of your scripts, so the syntax and behavior are consistent with each other.

------------

### notes on fucntion exepression:

warning in function exeprission ( anonymous function):

when you call it you can **only **call it using the variabl name

doWork();

```js
let doWork = function(){    
    return 0;
}

---------------

// you can name this function like this
let doWork = function doTheWork(){    
    return 0;
}


//but when you call it you can only call it by the variabl name

doWork();

doTheWork(); // reference error
```

------------------

ex: passing an exepression function as an arrgument

```js
// Function declaration that takes in two arguments: a function for displaying
// a message, along with a name of a movie
function movies(messageFunction, name) {
  messageFunction(name);
}

// Call the movies function, pass in the function and name of movie
movies(function displayFavorite(movieName){
//you can remove the fucntion name because it is an exepression 
  console.log("My favorite movie is " + movieName);
}, "Finding Nemo" 
//"Finding Nemo" is the second argument of "movies" funcion );
```

------------------

splice method 

variable.splice(index at which we will work, number of elements that will be removed , " values that will be added" )

```js
let months = ["January", "February", "Monday", "Tuesday"];
let days = months.splice(1,2, "March", "April");
//output:the removed part --> "Monday", "Tuesday"



//1 --> at which we will work
//2 --> number of values that will be taken
//  "March", "April" --> vakues that will be added


console.log(days);   // ["Monday", "Tuesday"] --> the removed part


console.log(months); // ["January", "February", "March", "April"]
                     // the array after being modified
```

------------------------

### objects:

conventional naming:

1. do not use quotes in naming properties, sometimes it causes a syntax error when using dot notation.

2. do not use numbers, hyphen and spaces in strarting naming properties.

----------------------

ex: for each with array of objects:

```js
var donuts = [
    { type: "Jelly", cost: 1.22 },
    { type: "Chocolate", cost: 2.45 },
    { type: "Cider", cost: 1.59 },
    { type: "Boston Cream", cost: 5.99 }
];

donuts.forEach(function(donut){
    console.log(donut.type + " donuts cost $" + donut.cost +" each" )
})

//
/*
output:
Jelly donuts cost $1.22 each
Chocolate donuts cost $2.45 each
Cider donuts cost $1.59 each
Boston Cream donuts cost $5.99 each
*/
```

-------------
