## DOM: 2

### Selecting By ID

In this section, we learned how to select a DOM element by its ID:

- `.getElementById()`

There are a couple of important things to keep in mind about this method:

- it is called on the `document` object
- it returns a *single* item

```js
// select the element with the ID "callout"
document.getElementById('callout');
```

NOTE:

if you use an nonexisted id, it will return **null**.

if you do not pass an id, it will return nothing.

----------------------------

### Accessing Elements By Their Class

note: watch out!! the "s" in elemnts 

```js
document.getElementsByClassName('brand-color');
```

----------------

### Accessing Elements By Their Tag

```js
document.getElementsByTagName('p');
```

note:

in tage name and class name : the list that's returned is not an array it is a HTML collection

**note!!!**

```js
document.getElementsByClassName("card")[0]; 
//get the first elemnt from the class                                             
```

------------

### The querySelector Method

We can use the `.querySelector()` method to select elements <u>**just like we do with CSS**</u>.

 We use the `.querySelector()` method and pass it a string that's just like a CSS selector:

```js
// find and return the element with an ID of "header"
document.querySelector('#header');

// find and return the first element with the class "header"
document.querySelector('.header');

// find and return the first <header> element
document.querySelector('header');
```

another ex: to find the first paragraph element that *also* has a class of: `callout`

```js
document.querySelector('p.callout');
```

note:

the `.querySelector()` method only **returns *one* element**. even if you use it to access a class or a tag .

-------------

### The querySelectorAll Method

-we use it when you will want to get a list of all elements with a certain class or all of one type of element( return multiple elemnts)

```js
// find and return a list of elements with the class "header"
document.querySelectorAll('.header');

// find and return a list of <header> elements
document.querySelectorAll('header');
```

ex: code to find all paragraph elements that are descendents of elements that have the class: `articles`

```js
document.querySelectorAll('.articles p');
```

-----------------
