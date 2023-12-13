## Testing Code Performance

The browser's `performance.now()` method starts measuring from the time the page loaded.

how to use: 

1. use `performance.now()` to get the **initial start time** for the code
2. run the code you want to test
3. execute `performance.now()` to get another time measurement **(final time)**
4. **subtract** the initial time from the final time

```js
const startingTime = performance.now();

for (let i = 1; i <= 100; i++) { 
  for (let j = 1; j <= 100; j++) {
    console.log('i and j are ', i, j);
  }
}

const endingTime = performance.now();
console.log('This code took ' + (endingTime - startingTime) + ' milliseconds.');
```

-----------------------------------

### Document Fragment:

-represents a minimal document object that <u>has no parent</u>. It is used as a lightweight version of Document that stores a segment of a document structure comprised of nodes just like a standard document.

-The key difference is that because the document fragment **<u>isn't part of the active document tree structure</u>**, changes made to the fragment don't affect the document, cause reflow, or incur any performance impact that can occur when changes are made.

-so we use `.createDocumentFragment()`

```js
const fragment = document.createDocumentFragment(); 
 // ← uses a DocumentFragment instead of a <div>

for (let i = 0; i < 200; i++) {
    const newElement = document.createElement('p');
    newElement.innerText = 'This is paragraph number ' + i;

    fragment.appendChild(newElement);
}

document.body.appendChild(fragment);  
// reflow and repaint here -- once 
```

-------------------

### **Reflow & Repaint**

**Reflow** is the process of the browser laying out the page. It happens when you first display the DOM (generally after the DOM and CSS have been loaded), and happens again every time something could change the layout. This is a fairly *expensive* (slow) process.

**Repaint** happens after reflow as the browser draws the new layout to the screen. This is fairly quick, but you still want to limit how often it happens.
