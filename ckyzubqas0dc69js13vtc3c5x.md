## Array Helper Methods: Every Javascript Developer Must know ! 😯

# 1. forEach

array.forEach() method is going to simply iterate all the elements in array.

Using with array.forEach() 
```
let userData=['Raj','kumar','Thangavel'];
userData.foreach((data,index)=>{
   console.log(index); // Index of the array
   console.log(data) // Raj, Kumar, Thangavel
})
```
Without using array.forEach() 
```
let userData=['Raj','kumar','Thangavel'];
for(let i=0;i<userData.length;i++){
   console.log(i); // Index of the array
   console.log(userData[i]) // Raj, Kumar, Thangavel
}
``` 
# 2. map

1. iterate all the elements in input array.
2. It's return a new array.

using using array.map() 
```
const userData = ["raj","kumar"];
let newUserData = userData.map((user)=>user)
console.log(newUserData);  // raj, kumar
```
Without using array.map() 
```
const userData = ["raj","kumar"];
let newUserData = [];
for(let i = 0; i < userData.length; i++){
    newUserData.push(arr[i])
}
console.log(newUserData);  // raj, kumar
```
# 3. filter

1. Iterate all the elements in input array and we need to write some condition and return it. Basically condition is return boolean (True/False). 
2. If It is return true, each data will be return. If It is return false, data will not return.
3. It's return a new array.

with using array.filter()
```
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6); // Conditions will return boolean only.

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```
without using array.filter()
```
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result=[];
for(let i=0;i<words.length;i++){
    if(word.length > 6){
        result.push(words[i])
    }
}

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```
# 4.find

1. It helps to find the value in array (only the first value).
2. It is return value only.

with using arrary.find()
```
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// expected output: 12
```
without using arrary.find()
```
const array1 = [5, 12, 8, 130, 44];

let found;

for(let i=0;i<array1.length;i++){
    if(element => element > 10){
       found=array1[i];
       break;
    }
}

console.log(found);
// expected output: 12
```
# 5. Reduce

1. It's going to take two Parameters. The first is the **previousValue** and the second is the **currentValue**.

2. previousValue is which we return the every elements along with arithmetic operation.

3. currentValue is each of the elements in arrary.

Let’s understand this method with an example:

```
const array1 = [1, 2, 3, 4];

let result=array1.reduce((previousValue, currentValue) => previousValue + currentValue);
// 1 + 2 + 3 + 4

console.log(result)
// expected output: 10

```
Without using Reduce method, 

```
const array1 = [1, 2, 3, 4];
let result=0;
for(let i=0;i<array1.length;i++){
result=result+array1[i]
}
console.log(result); 
// expected output: 10

```

# 6. Some

1.  It is return boolean. (True/False)
2. At least one elements will be matched with condition and it will return **true** or else It will return **false**.


with using Some method,
```
const inputArray = [1, 2, 3, 4, 5];

// checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(inputArray.some(even));
// expected output: true

```

without using Some method

```
const inputArray = [1, 2, 3, 4, 5];
let result;
for(let i=0;i<inputArray.length;i++){
     if(inputArray[i]% 2 === 0){
         result=true;
         break;
     }else{
           result=false;
     }
}
console.log(result);
// expected output: true
```
# 7. Every 

1.  It is return boolean. (True/False)
2. Every Each of the elements will be matched with one condition and it will return **true** or else It will return **false**.

with using Every method,

```
const array1 = [1, 30, 39, 29, 10, 13];

const isBelowThreshold = (currentValue) => currentValue < 40;

console.log(array1.every(isBelowThreshold));
// expected output: true

```
without using Every method,

```
const array1 = [1, 30, 39, 29, 10, 13];
let result;
for(let i=0;i<array1.length;i++){
     if(array1[i]<40){
        result=true;
     }else{
        result=false;
       break;
    }
}

console.log(result);
// expected output: true

```
# 8. FindIndex

1. This method return Index value.
2. It will return index of the first element based on the input value condition. Otherwise It will return -1.

with using FindIndex method,

```
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// expected output: 3

```
without using FindIndex method,

```
const array1 = [5, 12, 8, 130, 44];
let indexValue;

const isLargeNumber = (element) => element > 13;

for(let i=0;i<array1.length;i++){
    if(array1[i] > 13){
      indexValue=i;
      break;
    }else{
      indexValue=-1;
    }
}
console.log(indexValue);
// expected output: 3

```

# 9. Keys

Keys method helps to return  each index in the array.

with using Keys method,
```
const array1 = ['a', 'b', 'c'];
const iterator = array1.keys();

for (const key of iterator) {
  console.log(key);
}

// expected output: 0
// expected output: 1
// expected output: 2
```

without using Keys method,

```
const array1 = ['a', 'b', 'c'];
for(let i=0;i<array1.length;i++){
    console.log(i);
}
// expected output: 0
// expected output: 1
// expected output: 2
```

# 10. values

The values method returns each element in the array.

with using values method,
```
const array1 = ['a', 'b', 'c'];
const iterator = array1.keys();

for (const value of iterator) {
  console.log(key);
}

// expected output: a
// expected output: b
// expected output: c
```

without using values method,

```
const array1 = ['a', 'b', 'c'];
for(let i=0;i<array1.length;i++){
    console.log(array1[i]);
}
// expected output: a
// expected output: b
// expected output: c
```

Don't existing legacy code, Use Array helper Methods. It is simple and reduce your code . 

## My resent blog: 

#### [**Top ES6 Features - Every Javascript Developer Must know...! *](Top ES6 Features - Every Javascript Developer Must know...! 🤔)*🤔

https://thisisraj.hashnode.dev/top-es6-features-every-javascript-developer-must-know