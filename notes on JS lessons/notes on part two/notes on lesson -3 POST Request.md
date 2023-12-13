## POST request:

-we use `.post()`method

-HTTP POST request sends data to the project's endpoint,

```js
// POST method route
app.post('/', function (req, res) {
  res.send('POST received')
})
```

```js
//First, Create an array to hold data:
const data = []

//Then, create post() with a url path and a callback function:
app.post('/addMovie', addMovie )

//In the callback function, add the data received from request.body
//This is a piece of information from the request (req) argument returns.
function addMovie (req, res){
   console.log(req.body)
   data.push(req.body) //we use push to post the 
}
```
