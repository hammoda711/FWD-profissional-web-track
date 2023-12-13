### .innerHTML

We can use this property to:

- get(return) an element's (and all of its descendants!) HTML content(as a string)
- set an element's HTML content

innerHTML VS outerHTML:

```js
<h1 id="pick-me">Greetings To <span>All</span>!</h1>

const innerResults = document.querySelector('#pick-me').innerHTML;

console.log(innerResults); 
// logs the string: "Greetings To <span>All</span>!"

const outerResults = document.querySelector('#pick-me').outerHTML;
console.log(outerResults); 
//logs the string :"<h1 id="pick-me">Greetings To <span>All</span>!</h1>"
```

----------------

### .textContent

This property will:

- set the text content of an element and all its descendants
- return the text content of an element and all its descendants
- note: it returns the text <u>regardless </u>the CSS effect.

**note !!!**

If you'd like to update an element, *including* its HTML, then you need to use the `.innerHTML` property:

```js
myElement.textContent = 'The <strong>Greatest</strong> Ice Cream Flavors'; // doesn't work as expected

myElement.innerHTML = 'The <strong>Greatest</strong> Ice Cream Flavors';  // works as expected
```

------------

### .innerText

`.innerText` will get the *visible* text of the element. This is an important distinction! If CSS is used to hide any text inside that element, `.innerText` *will not* return that text, while `.textContent` *will* return it.

note:  Rarely will you actually want *only* the *visible* text, and it is not supported in all browsers.

-------------------

ex:

we can change elements and also we can just show them 

by `innerHTML, innerText, textContent`

```js
const excitedText = document.createElement('span');

excitedText.textContent = '!!!';
z.appendChild(excitedText);
//<span>​!!!​</span>

console.log(z);
// <label>​…​</label>​

console.log(z.innerHTML);
//<span>!!!</span>        
//note: the result is the whole tag

console.log(z.innerText);
// !!!

console.log(z.textContent);
// !!!

z.innerHTML = 'The <strong>Greatest</strong> Ice Cream Flavors';
console.log(z.textContent);
//The Greatest Ice Cream Flavors

z.innerText = "yaya";
console.log(z.textContent);
// yaya

```
