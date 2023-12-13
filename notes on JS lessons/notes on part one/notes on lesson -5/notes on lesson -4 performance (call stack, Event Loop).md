## call stack:

-it is used to manage the excution context,

-it is LIFO 

-script will stop when the stack is empty

-the call stack has a fixed size, it causes the problem of "overflow", it is solved via browser or using node js.

## The JavaScript Event Loop

The simplest explanation of JavaScript's *concurrency model* uses two rules:

- If some JavaScript is running, let it run until it is finished ("run-to-completion").

- If no JavaScript is running, run any pending event handlers.

**event loop**: Pick up the next event, run its handler, and repeat.

-

There are three parts you have to think about around the event loop:

- the Call Stack
- Web APIs/the browser
- an Event Queue

<img src="https://video.udacity-data.com/topher/2017/December/5a31c70d_l4-performance-js-the-dom/l4-performance-js-the-dom.jpg" title="" alt="" width="503">

-IMPORTANT:

 **The key things to remember here are**

1) current synchronous code runs to completion

2) events are processed when the browser isn't busy.(events wait in the Event Queue until the call stack becomes not busy)

3) Asynchronous code (such as loading an image) runs outside of this loop and sends an event when it is done.

<img src="file:///C:/Users/nile%20company/AppData/Roaming/marktext/images/2022-04-05-18-13-37-image.png" title="" alt="" width="557">

-note:

 Any asynchronous code (like `setTimeout` or the function passed to `.addEventListener()`) is handled by the browser. When this asynchronous code is ready to be executed, it's moved to the queue where it waits until the Call Stack is empty.
