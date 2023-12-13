## Node js

node js is an 

1. open source 

2. cross platform 

3. server side 

4. persistence

----------------------------

### installing packages

-to install <u>packages </u>with NPM from the command line: 

`npm install package-name`

-to install the <u>package </u>called ‘body-parser’:

 `npm install body-parser`

-And then in a file named `Server.js` the installed package is included and made available in the code with: 

`const bodyParser = require('body-parser')`

-Node invokes that `require()` function with a local file path as the function’s only argument.

------------------------------------------------------------------

### express:

-Express is a <u>package</u> for Node that allows server side programming with connected middleware and with HTTP routes and easy handlers for requests.

-Express is a package for Node that allows you to build routes and handlers to interact with Web APIs

-we use `.use()`method to connect the other packages we have installed on the command line to our app in our code.

```js
/* Dependencies */
const bodyParser = require('body-parser')
/* Middleware*/
//Here we are configuring express to use body-parser as middle-ware.
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());
// Cors for cross origin allowance
const cors = require('cors');
app.use(cors());
```

---

- **Server-side**: It refers to operations performed by the server in a network. In web development, we used the *Server-side scripting* technique to employ scripts on a web server that produces a response for each user's request.

- **Client-side**: It refers to operations performed at the client or user's end.

- **Package**: It is a file or directory defined by a `package.json`. The npm registry contains many packages which are node modules or include node modules.

- **Module**: Any file or directory in the `node_modules` directory that can be loaded by the Node.js `require()` function is known as a module.
