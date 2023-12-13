## events:

### intro:

**event**: looks like an announcement  that we use JS to listen it and respons to it.

-Chrome browser has a special `monitorEvents()` function that will let us see different events as they are occurring.

-`monitorEvents()` is used for testing purpose only.

-`unmonitorEvents()` function that will turn off the announcing of events for the targeted element

```js
// start displaying all events on the document object
monitorEvents(document);

unmonitorEvents(document);
// turn off the displaying of all events on the document object.
```

----------------

### event target:

EventTarget:

-is an interface implemented by objects that can receive events and may have listeners for them.

-and Element, document, and window are the most common event targets, but other objects can be event targets too…

![A diagram showing EventTarget inherited by all nodes and elements](https://video.udacity-data.com/topher/2017/December/5a22d197_ud117-l1-interface-chain/ud117-l1-interface-chain.jpg)

*The EventTarget Interface is inherited by all nodes and elements.*

 ----------------------------

### the eventTarget interace

the EventTarget Interface **<u>does not have</u> *any* properties and only three methods!** These methods are:

- `.addEventListener()`
- `.removeEventListener()`
- `.dispatchEvent()`

--------------------------

### .addEventListener()

Using the `.addEventListener()` method will let us ***listen*** for events and ***respond*** to them! 

 "*listen for* events". There are several ways to "phrase" this, so I want to give some examples:

- listen for an event
- listen to an event
- hook into an event
- respond to an event

```js
//<event-target>.addEventListener(<event-to-listen-for>, <function-to-run-when-an-event-happens>);

target.addEventListener(type, listener);
//للتوضيح فقط target.addEventListener(event, response)
```

So an event listener needs three things:

1. an event target - this is called the **target**
2. the type of event to listen for - this is called the **type**
3. a function to run when the event occurs - this is called the **listener**

ex:

```js
const mainHeading = document.querySelector('h1');

mainHeading.addEventListener('click', function () {
  console.log('The heading was clicked!');
});
```

-----------------

### .removeEventListener()

-to remove an event listener you must use the same target, type and response(listener).

-tricky note!!!!!!!!!!

the fucntion that is the listener in the `.removeEventListener()` and `.addEventListener()` must be the same function not two equal function, by other words, the two functions must point to the same reference in the memory.

ex: work well

```js
function myEventListeningFunction() {
    console.log('howdy');
}

// adds a listener for clicks, to run the `myEventListeningFunction` function
document.addEventListener('click', myEventListeningFunction);

// immediately removes the click listener that should run the `myEventListeningFunction` function
document.removeEventListener('click', myEventListeningFunction);  


//it will remove the click listener
```

ex: did not work 

```js
// adds a listener for clicks, to run the `myEventListeningFunction` function
document.addEventListener('click', myEventListeningFunction);

// immediately removes the click listener that should run the `myEventListeningFunction` function
document.removeEventListener('click', myEventListeningFunction);


//it will not remove the click listener
```

![Two functions can look the same, but live in two different places in memory. Looks can be deceiving!](https://video.udacity-data.com/topher/2020/April/5ea20aaf_screen-shot-2020-04-23-at-2.37.30-pm/screen-shot-2020-04-23-at-2.37.30-pm.png)
