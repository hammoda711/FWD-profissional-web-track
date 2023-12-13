## API, acync fetch API,

API: application programing interface

### async fetch API:

1. sign up for dev credential and get API key (for free ).

2. build query by API URL include using API key

then add fetch to code:

```js
let baseURL = 'http://api.animalinfo.org/data/?animal='
let apiKey = '&appid=9f15e45060...';
const newAnimal =  document.getElementById('animal').value;

const generateEl = document.getElementById('generate');
generateEl.addEventListener('click', performAction);

function performAction(e){
getAnimal(baseURL,newAnimal, apiKey)
}


const getAnimal = async (baseURL, animal, key)=>{

  const res = await fetch(baseURL+animal+key)

  try {
    const data = await res.json();
    console.log(data)
    return data;
  }  

catch(error) {
    console.log("error", error);
    // appropriately handle the error
  }
}
```

-----------

dynamic URL:

`'base url='+holdervariablename+key`

ex:

`'www.api.com/data?='+holder+68`

------------------------------------------------------------------
