# JavaScript Snippets

## 1. Correct below JS code
```javascript
const length = 4;
const numbers = [];
for (var i = 0; i < length; i++);{
  numbers.push(i + 1);
}
console.log(numbers);
```
## Output & Correction
```output
[ 5 ]   for loop ';' needs to remove
Expected Output : [1,2,3,4]
```
## 2. What will be the output of below JS code
```javascript
const clothes = ['jacket', 't-shirt'];
clothes.length=0;
console.log(clothes[0]);
```
## Output & Explanation
```output
undefined
clothes.length = 0; deletes the array and hence clothes[0] does not exist
```
## 3. Write JS code for for multiply by 3 it should come 'Fizz' and for 5 'Buzz' and for 15 it should come 'FizzBuzz'
```javascript
for (var i = 1; i <= 100; i++) {
    if (i % 15 == 0) console.log("FizzBuzz");
    else if (i % 3 == 0) console.log("Fizz");
    else if (i % 5 == 0) console.log("Buzz");
    else console.log(i);
}
```
## Output
```output
1 2 Fizz 4 Buzz Fizz 7 8 Fizz Buzz 11 Fizz 13 14 FizzBuzz 16 17 Fizz 19 Buzz Fizz 22 23 Fizz Buzz 26 Fizz 28 29 FizzBuzz 31 32 Fizz 34 Buzz Fizz 37 38 Fizz Buzz 41 Fizz 43 44 FizzBuzz 46 47 Fizz 49 Buzz Fizz 52 53 Fizz Buzz 56 Fizz 58 59 FizzBuzz 61 62 Fizz 64 Buzz Fizz 67 68 Fizz Buzz 71 Fizz 73 74 FizzBuzz 76 77 Fizz 79 Buzz Fizz 82 83 Fizz Buzz 86 Fizz 88 89 FizzBuzz 91 92 Fizz 94 Buzz Fizz 97 98 Fizz Buzz

```
## 4. Write an example of function currying
```javascript
console.log(sum(1)(2)(3)(4));

function sum(a){
    return function(b){
        return function(c){
            return function(d){
                return a+b+c+d;
            }
        }
    }
}
```
## Output
```output
10
```
## 5. Write an example of infinite currying
```javascript
console.log(sum(1)(2)(3)(4)(7)());

function sum(a){
    return function(b){
        if (b) return sum(a+b);
        return a;
    }
}
```
## Output
```output
17
```
## 6. Remove any element from array
```javascript
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0];
    var removed = arr.splice(1,3); // 1 starting position of array and 3 is ending position of an array 
    
    console.log(arr);
```
## Output
```output
[ 1, 5, 6, 7, 8, 9, 0 ]

```

## 7. What will be the output of the below code
```javascript
console.log(![]);
console.log([] !== []); // it should be uneuql then it will give 'true'
console.log([]===![])
```
## Output & Explanation
```output
false
true
false
-> Both empty array objects are kept in diff. memory location and both are different
```
## 8. Deep copy & Shallow copy
```javascript

const student={
    name:'kuldeep',
    age:24,
    address: {
                street:'Hinjewadi',    
                city:'Pune'
    
             }
}

let s2={
    ...student,                           //Shallow Copy
}
console.log(s2);

let s3=Object.assign({},student) //Shallow Copy
console.log(s3);

let s4=JSON.parse(JSON.stringify(student)); //Deep copy
s4.address.city='Nagpur';
console.log(s4);

```
## Output
```output
{
  name: 'kuldeep',
  age: 24,
  address: { street: 'Hinjewadi', city: 'Pune' }
}
{
  name: 'kuldeep',
  age: 24,
  address: { street: 'Hinjewadi', city: 'Pune' }
}
{
  name: 'kuldeep',
  age: 24,
  address: { street: 'Hinjewadi', city: 'Nagpur' }
}

```

