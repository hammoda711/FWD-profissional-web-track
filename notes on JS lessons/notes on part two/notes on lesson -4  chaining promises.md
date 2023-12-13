## chaining promises:

-chaining promises: on top of each other.

-we using `.then` function for chaining promises.

-we need to do two fetch calls:

1. GET to the web API

2. POST to  store the data we received localy

3. then usnig `.then` function for chaining

```js
//client code
  .then(function (data){
     console.log(data)
 //add data to post request
 postdata('/path', {animal:data.animal,fact:data.fact, fav :fav});
  //fav is from user so we do not use dot notation 
 });

//in the try statment we need to return "newEntry"
```

```js
//server code 
const animalData = [];
//GET REQUEST 
//


//POST REQUEST
function addAnimal(req, res){
newEntry = { 
animal: req.body.animal,
facts: req.body.fact,
fav: req.body.fav
} 

//and push the entry data
animalData.push(newEntry)
res.send(animalData)
}
```
