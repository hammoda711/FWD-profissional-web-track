### control the page style

**`.style.property`**

```js
const mainHeading = document.querySelector('h1');

mainHeading.style.color = 'red'; 
mainHeading,style.fontSize = "15px"
```

------------

**`.style.cssText`** : property to set **multiple** CSS styles at once!

```js
const mainHeading = document.querySelector('h1');

mainHeading.style.cssText = 'color: blue; background-color: orange; font-size: 3.5em';

//
```

note: `font-size` like in CSS, not `fontSize`

---------------------

## Accessing an Element's Classes

### **`.className`**

```js
const mainHeading = document.querySelector('#main-heading');

// store the list of classes in a variable
const listOfClasses = mainHeading.className;

console.log(listOfClasses); 
// logs out: the string "ank-student jpk-modal" بينهم مسافة

const arrayOfClasses = listOfClasses.split(' ');
console.log(arrayOfClasses);
// logs out: the array of strings ["ank-student", "jpk-modal"]
```

note: `.className` **return a string,** so it is difficult to to add or remove individual classes

-----------

### **`.classList`** (recommended to use)

-it returns a `domTokenList`

-The `.classList` property has a number of properties of its own. Some of the most popularly used ones are:

- `.add()` - to add a class to the list
- `.remove()` - to remove a class from the list
- `.toggle()` - to add the class if it doesn't exists or remove it from the list if it does already exist
- `.contains()` - returns a boolean based on if the class exists in the list or not

ex:

```js
//HTML
//<h1 id="main-heading" class="ank-student jpk-modal">Learn Web Development at Udacity</h1>


const mainHeading = document.querySelector('#main-heading');

mainHeading.classList.toggle('richard');
```

------------------
