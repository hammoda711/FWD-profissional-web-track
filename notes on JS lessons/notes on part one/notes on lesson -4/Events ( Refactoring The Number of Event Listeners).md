### refactoring Refactoring The Number of Event Listeners

```js
const myCustomDiv = document.createElement('div');

for (let i = 1; i <= 200; i++) {
    const newElement = document.createElement('p');
    newElement.textContent = 'This is paragraph number ' + i;

    newElement.addEventListener('click', function respondToTheClick() {
        console.log('A paragraph was clicked.');
    });

    myCustomDiv.appendChild(newElement);
}

document.body.appendChild(myCustomDiv);

//in this code there are 200 events and 200 respondToTheClick() function
//it is too wasty to the memory  
```

after refactoring :

```js
onst myCustomDiv = document.createElement('div');

function respondToTheClick() { //one function outside the for loop
    console.log('A paragraph was clicked.');
}

for (let i = 1; i <= 200; i++) {
    const newElement = document.createElement('p');
    newElement.textContent = 'This is paragraph number ' + i;

    myCustomDiv.appendChild(newElement);
}

myCustomDiv.addEventListener('click', respondToTheClick);
//one event outside the for loop

document.body.appendChild(myCustomDiv);
```

---------------------------------------

### .target property

-returns the element that triggered the event.

```js
للتوضيح
target.addEventListener('click', function(){ ... })

//"event.target" refers to the element in the target place 
```

--------------

### .nodeName

-Return the node name of an element:

```html
<!DOCTYPE html>
<html>
<body>

<div>The node name of the "demo" element is:
<div id="demo"></div>
</div>
<script>
let text = document.getElementById("demo").nodeName;
document.getElementById("demo").innerHTML = text;
</script>

</body>
</html> 

// the output is DIV (in capital case)
```

note:

The `.nodeName` property will return a *capital* string, not a *lowercase* one. So when you perform your check make sure to either:

- check for capital letters
- convert the `.nodeName` to lowercase

```js
// check using capital letters
if (evt.target.nodeName === 'SPAN') {
    console.log('A span was clicked with text ' + evt.target.textContent);
}

// convert nodeName to lowercase
if (evt.target.nodeName.toLowerCase() === 'span') {
    console.log('A span was clicked with text ' + evt.target.textContent);
}
```

-----------------

### .preventDefaut():

-Without the event object, we're stuck with the default actions.

-an advantage of the event object is that you can stop the event or prevent it.

```js
const links = document.querySelectorAll('a');
const thirdLink = links[2];

thirdLink.addEventListener('click', function (event) {
    event.preventDefault();
    console.log("Look, ma! We didn't navigate to a new page!");
});
```

---
