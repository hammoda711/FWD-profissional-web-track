## Processing the POST request(in server side)

-we attached our data to the `body` of our POST request, so to receive that data and make it actionable we can use `request.body`.

```js
app.post('/add', function (request, response) {
    let data = request.body;
    console.log(data);
});
```

-if the data received from the POST request was `{intelligence:100}`, we could create a new entry in our endpoint with the code:

```js
let data = request.body; 
projectData["intelligence"]= data.intelligence;
```
