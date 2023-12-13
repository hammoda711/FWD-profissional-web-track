## DOM: important concepts before the DOM!!

### Destructuring:

allowing you to specify the elements you want to extract from an array or object *on the left side of an assignment*.

ex: destructuring from array:

```js
const point = [10, 25, -34];

const [x, y, z] = point;

console.log(x, y, z);
```

ex: destructuring from object:

```js
const gemstone = {
  type: 'quartz',
  color: 'rose',
  carat: 21.29
};

const {type, color, carat} = gemstone;

console.log(type, color, carat);
```

----------

object literals:

```js
let type = 'quartz';
let color = 'rose';
let carat = 21.29;

const gemstone = {//ignore redundent 
  type,
  color,
  carat,
  calculateWorth: function() {
return "30"  }
};
```

the same ex:

```js
let type = 'quartz';
let color = 'rose';
let carat = 21.29;

const gemstone = {
  type,
  color,
  carat,
  calculateWorth() { //tou can ignore the function word and the colon:
return "30"  }
};
```

------------

### for loop family:

##### for loop:

```js
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (let i = 0; i < digits.length; i++) {
  console.log(digits[i]);
}
```

##### for . . in:

```js
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const index in digits) {
  console.log(digits[index]);
}
```

-for . . in need to access the properties by index

-has a problem in adding object properties( error)

##### for .. of:

```js
onst digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits){
 if (digit % 2 === 0) {
    continue;                     //break at any time
  }           
  console.log(digit);
}
```

-you can stop or break a for...of loop at anytime.

-you don’t have to worry about adding new properties to objects

------------------

### The **spread operator**:

written with three consecutive dots ( `...` ), is new in ES6 and gives you the ability to expand, or *spread* into multiple elements, such as concatinate two arrays in one array.

```js
const fruits = ["apples", "bananas", "pears"];
const vegetables = ["corn", "potatoes", "carrots"];

const produce = [...fruits,...vegetables];

console.log(produce);


//output: [ 'apples', 'bananas', 'pears', 'corn', 'potatoes', 'carrots' ]
```

---------------------

### Rest parameter:

The **rest parameter**, also written with three consecutive dots ( `...` ), allows you to represent an indefinite number of elements as an array. This can be helpful in a couple of different situations.

One situation is when assigning the values of an array to variables. For example,

```js
const order = [20.17, 18.67, 1.50, "cheese", "eggs", "milk", "bread"];
const [total, subtotal, tax, ...items] = order; //array destructuring
console.log(total, subtotal, tax, items);


//output: ** 20.17 18.67 1.5 ["cheese", "eggs", "milk", "bread"]
```

anorher use for the rest parameter is in the variadic function:

```js
function sum(...nums) { //using the rest parameter 
  let total = 0;  
  for(const num of nums) {
    total += num;
  }
  return total;
}
```

---------------
