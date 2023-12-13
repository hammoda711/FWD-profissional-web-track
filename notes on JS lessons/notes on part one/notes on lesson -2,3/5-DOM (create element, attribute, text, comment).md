## create element, attribute, text, comment

`document.createElement("element")`:

`document.createAttrribute("")`:

`document.createTextNode("")`:

`document.ceateComment("")`:

### appendCHhild():

note:

-Creating an element...just creates it. **It doesn't add it to the DOM!!!!!!!,**

-We can use the `.appendChild()` method to add an element to the page!

```js
// create a brand new <span> element
const newSpan = document.createElement('span');

// select the first (main) heading of the page
const mainHeading = document.querySelector('h1');

// add the <span> element as the last child element of the main heading
mainHeading.appendChild(newSpan); 
```

notes on appendChild():

-it must take an argument 

-it can not be used for <u>object </u>, it must be used for <u>elemnt</u>.

```js
const newSpan = document.createElement('span');

// causes an error!!!!!!!!!!!!!!!!!!!
document.appendChild(newSpan);
```

note:

```js
const mainHeading = document.querySelector('#main-heading');
const otherHeading = document.querySelector('#other-heading');
const excitedText = document.createElement('span');

excitedText.textContent = '!!!';
mainHeading.appendChild(excitedText);
otherHeading.appendChild(excitedText);
```

at the end only the (otherHeading) has the "! ! !", **becuase appendChild() move the elemnt from its place to the new place**

---

### .insertAdjacentHTML()

method has to be called with two arguments:

- the location of the HTML
- the HTML text that is going to be inserted

```html
locations

<!-- beforebegin -->
<p>
    <!-- afterbegin -->
    Existing text/HTML content
    <!-- beforeend -->
</p>
<!-- afterend -->
```

```js
const mainHeading = document.querySelector('#main-heading');
const htmlTextToAdd = '<h2>Skydiving is fun!</h2>';

mainHeading.insertAdjacentHTML('afterend', htmlTextToAdd);
```

note: !!!!!!!!!!

**that the second argument must be text, if it is an HTML it will be ignored.**

-------------------------

### notes on this lesson

Some important things to note are:

- if an element *already exists in the DOM* and this element is passed to `.appendChild()`, the `.appendChild()` method will *move it* rather than duplicating it
- an element's `.textContent` property is used more often than creating a text node with the `.createTextNode()` method
- the `.insertAdjacentHTML()` **method's second argument has to be tex**t, you can't pass an element

------------------

### removeChild():

`.appendChild()` method, the `.removeChild()` method requires:

- a parent element
- the child element that will be removed

```
<parent-element>.removeChild(<child-to-remove>);
```

another way:

```js
const mainHeading = document.querySelector('h1');

mainHeading.parentElement.removeChild(mainHeading);
```

`parentElement` is a property that focus on the element's parent, **so you do not need to use the parent itself****

note:

the difference between `.firstChild` and `.firstElementChild`, is that

`.firstElementChild` will always return the first element, 
while `.firstChild` *might* return whitespace (if there is any) to preserve the formatting of the underlying HTML source code.

 -----------------------------

### easier way !!!!!

use the `remove()` method 

```js
const mainHeading = document.querySelector('h1');

mainHeading.remove();
```

--------------------------
