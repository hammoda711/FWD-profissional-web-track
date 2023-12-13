## creating local server:

#### 

```js
// set the port 
const port = 8000;

//create the server using ".listen()" 
const server = app.listen(port, listening);

function listening(){
     console.log("server running"); 
     console.log(`running on localhost: {$port}`);
}
```

--------------------------------

### arrow function

Arrow functions are a shorter, more efficient way to write functions.

Here's another example of a regular function and then we'll write it as an arrow function:

**Regular Function**

`function addition(number){ return 4 + number }`

`addition(4);` `

**Arrow Function**

`const addition = number => 4 + number`

`addition(4);`

advantages of use arrow function :

here is less need for parenthesis and return statements, 

allowing the syntax to be much more compact. Both are acceptable ways of writing functions, and best practice

------------------

### full local server code

```js
/* Empty JS object to act as endpoint for all routes */
projectData = {};


// Express to run server and routes
const express = require('express');


// Start up an instance of app
const app = express();


/* Dependencies */
const bodyParser = require('body-parser')
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());



// Cors for cross origin allowance
const cors = require('cors');
app.use(cors());


/* Initializing the main project folder */
app.use(express.static('website'));

//set server to a port 
const port = 8000;

//create the server using ".listen()" 
const server = app.listen(port, listening);

function listening(){
     console.log("server running"); 
     console.log(`running on localhost: ${port}`);
}; 
```

-----------

### important note!!!!

-the file of server.js (in our case "localServer.js") is **outside and in the same level** of the folder of the client side ()which contain html, css, js files) 

![](C:\Users\nile%20company\AppData\Roaming\marktext\images\2022-04-09-16-33-15-image.png)

so, in the `server.js` file the following line of code needs to be added:

`app.use(express.static('website'));`

 ------------------
