## even life cycle

### phases of event:

![A diagram showing the three event phases of an event: capturing, at target, and bubbling.](https://video.udacity-data.com/topher/2017/December/5a2f0488_ud117-phases-of-event-flow/ud117-phases-of-event-flow.svg)

![](C:\Users\nile%20company\OneDrive\Pictures\Screenshots\Screenshot%20(21).png)

------------

### when response ?

there are two ways to make the listener response 

1- at bubbeling phase : by default without the third argument

```js
document.addEventListener('click', function () {
   console.log('The document was clicked');
});
```

2- at capturing phase : using the third argument setting it to "true"

```js
document.addEventListener('click', function () {
   console.log('The document was clicked');
}, true);
```

--------------------

**note on bubbeling:**

if we are in the bubbeling phase the **inner** event will be excuted **first**.

```js
document.addEventListener('click', function () {
   console.log('The document was clicked');
});

document.body.addEventListener('click', function () {
    console.log('The body element was clicked'); //will be excuted first 
});
```

--------------

note:

using an parameter for the response function, to store the event data that's passed to it!

```js
const items = document.querySelectorAll('.quizzing-quizzes');
const el = items[1];

el.addEventListener('keypress', function (event) { //event is just a name
    console.log('You clicked on the 2nd quizzing-quizzes item!');
});
```

------------------------
