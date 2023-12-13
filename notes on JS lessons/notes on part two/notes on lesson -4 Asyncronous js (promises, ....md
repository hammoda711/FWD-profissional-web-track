## Asyncronous js

### promises:(client side)

-Promises are now the accepted **best practice** for writing asynchronous functions in JavaScript.

-promises give you flexibility, intuitive syntax, and easy error handling.

Syntax:

```js
var promise = new Promise(function(resolve, reject) {
  // do a thing, possibly async, then…

  if (/* everything turned out fine */) {
    resolve("Stuff worked!");
  }
  else {
    reject(Error("It broke"));
  }
});
```

--------------

### async POST :(client side)

```js
const postData = async ( url = '', data = {})=>{

      const response = await fetch(url, {
      method: 'POST', // *GET, POST, PUT, DELETE, etc.
      credentials: 'same-origin', 
      headers: {
          'Content-Type': 'application/json',
      },
    // body data type must match "Content-Type" header
      body: JSON.stringify(data),         
    });

      try {
        const newData = await response.json();
               return newData
      }catch(error) {
      console.log("error", error);
      // appropriately handle the error
      }
  }

  postData('/addMovie', {movie:' the matrix', score: 5})
```

note: للتوضيح

Once you mark a function as 'async' you have access to the keywords `await`, `try`, and `catch`.

```js
try {
        const newData = await response.json();
        return newData
      }
catch(error) {
      console.log("error", error);
      // appropriately handle the error
      }
```

-The keywords `try` and `catch` mirror the Promise functionality of resolving or rejecting to execute a task. 

-In this case. `if `and`else`are replaced with the keywords`try`and`catch`

---------------

<img title="" src="https://video.udacity-data.com/topher/2020/June/5ee22585_screenshot-2020-06-10-at-3.39.36-pm/screenshot-2020-06-10-at-3.39.36-pm.png" alt="" width="449">

-----------------

### async GET request:

```js
const retrieveData = async (url='') =>{ 
  const request = await fetch(url);
  try {
  // Transform into JSON
  const allData = await request.json()
  }
  catch(error) {
    console.log("error", error);
    // appropriately handle the error
  }
}
```
