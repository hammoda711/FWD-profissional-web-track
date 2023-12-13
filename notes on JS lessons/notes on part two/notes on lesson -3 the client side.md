## the client side

```js
const postData = async (url = '', data = {})=>( 
cosole.log(data)
const response = await fetch(url,  {
      method: 'POST', 
      credentials: 'same-origin',
      headers: {
          'Content-Type': 'application/json',
      },
    //attached data to POST req body
      body: JSON.stringify(data), 
 })
postData('/add', {answer:42})
```

-When sending data to a web server, the data <u>has to be a string.</u> We can <u>convert </u>a JavaScript object into a <u>string </u>using the JavaScript method `JSON.stringify()`, which turns JavaScript objects and JSON data into a string for our server to receive the information.

-The `body` of the request is the part we are most interested in because this is how we will access the data on the server side
