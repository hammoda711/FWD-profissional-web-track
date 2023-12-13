## Routes & GET Requests

##### server:

1. receive requests 

2. process them 

3. return respose

##### routes:

-used to handle the requests

  -------------

##### two common types of requests:

GET: get data

POST: send data security

------------

note:

**express** provide methodes which define the routing, these method correspond to (HTTP methods).

------------------------------------------------------

example (GET request):

```js
var express = require('express');
var app = express();

// respond with "hello world" when a GET request is made to the homepage
app.get('/', function (req, res) {
 //using anonomous function
  res.send('hello world'); //look!! usnig send to send respond
})
```

-The `req` parameter signifies the "request" from the client to the server. The `res` parameter signifies the "response" from the server to the client.

------------------------

more powerfull example: (using a js object as an endpoint)

```js
var express = require('express')
var app = express()
// Create JS object
const appData = {}
// Respond with JS object when a GET request is made to the homepage

```

-we use new route named '/all', so that the route 'localhost:3000/all' will now trigger the GET request, which will return the JavaScript object as laid out in the server code above.

-------------------
