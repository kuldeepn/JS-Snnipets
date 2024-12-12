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

## 9. Write a code to check given string is palindrome or not
```javascript
var string = 'aba';

function pal(str){
    let res=str.split('').reverse().join("");
    if (res==str){
    console.log('Palindrome');
}
else{
    console.log('Not a Palindrome');
}
}
pal(string);
```
## Output & Explanation
```output
Palindrome
```

## 10. Call,Apply & Bind
```javascript
//Call

let userDetails={
    name:'kuldeep',
    age:28,
    city:'Pune'
}

function printDetails(city,country){
    console.log(this.name,''+city,''+country);
}

let userDetails2={
    name:'deepa',
    age:27,
    city:'Pune'
}

printDetails.call(userDetails);
printDetails.call(userDetails2);

//Apply
printDetails.apply(userDetails,['Nagpur','India']);

//Bind
let newFun=printDetails.bind(userDetails2,'Nagpur','Nepal');

newFun();
```
## Output & Explanation
```output
kuldeep undefined undefined
deepa undefined undefined
kuldeep Nagpur India
deepa Nagpur Nepal
```
## 11. Find the duplicate element and count of an array
```javascript
let duplicateArray=[1,3,4,3,6,1,1];

function duplicate(ele,index,arr){
    return arr.indexOf(ele) !== index;
}

const dup=duplicateArray.filter(duplicate);

const uniqueDup=[...new Set(dup)]  //It will give the unique duplicates

console.log(uniqueDup)

//Count
let count =uniqueDup.length;
console.log('Count =',count);
```
## Output & Explanation
```output
[ 3, 1 ]
Count = 2
```
## 12. JS code to sort a Number array
```javascript

let sortArray=[1,5,65,56,55,2,5,6];

let newArray=sortArray.sort((a,b)=>{
    return a-b;
})

console.log(newArray);

```
## Output & Explanation
```output
[1, 2, 5, 5, 6, 55, 56, 65]

```

## 13. Reverse word in a string without changing it's position
```javascript

var str="Welcome to Programiz";

function xyz(strl){
    
    let words=strl.split(' ');
    
  let res=words.map(x=>
      x.split('').reverse().join(''));
       
  return res.join(' ')
   
}

let rev=xyz(str);

console.log(rev)

```
## Output & Explanation
```output
emocleW ot zimargorP

```
## 14. Function Borrowing
```javascript

const person = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () {
    return this.firstName + " " + this.lastName;
  }
}

const member = {
  firstName:"Hege",
  lastName: "Nilsen",
}

let fullName = person.fullName.bind(member);

console.log(fullName());

```
## Output & Explanation
```output
Hege Nilsen

```
## 15. Another way to do function currying
```javascript

// add(2)(3)(4) => 9

// add(2)(3) => 5

// add(2)(3)(4)(9) => 18

function add(a){
    let v= function(b){
      return add(a+b);
    }
     v.valueOf = v.toString = function() {
    return a;
  };
    return v;
}

console.log(+add(2)(3)(4)(4));

```
## Output & Explanation
```output
13
Explanation: + operator will invoke valueOf and valueOf will give primitive value from function
```
## 16. What is the output of the following
```javascript

function x(){
    for(var i=1;i<=5;i++){   
        setTimeout(()=>{
            console.log(i);
        },1000)
    }
    console.log("Namaste Javascript")
}

x()

```
## Output & Explanation
```output
Namaste Javascript
6
6
6
6
6
- Issue with var in the for loop: var is function-scoped, so the variable i doesn't maintain its value in each iteration due to how closures work in JavaScript. Instead, it will log 6 five times because by the time the setTimeout callback executes, the loop has already finished and i has a value of 6.
- To fix the issue with var, you can either use let
```

## 17.  What is the output of the following
```javascript
console.log(typeof typeof 1)
```
## Output & Explanation
```output
string
typeof 1: The typeof operator returns the type of its operand. Since 1 is a number, typeof 1 evaluates to the string "number".

typeof "number": Now, the typeof operator is applied again to "number", which is a string. So, typeof "number" evaluates to "string".
```
## 18. Promise example
```javascript
const promiseFun= new Promise((resolve,reject)=>{
   let success=true;
    
    if(success){
        resolve("success");
    }else{
        reject("rejected")
    }
})

promiseFun.then((msg)=>{
    console.log(msg)
}).catch((msg)=>{
    console.log(msg)
})
```
## Output & Explanation
```output
success
```
## 19. const obj = [{apple: 2, orange: 1, banana: 3, grapes: 1},{apple: 2, orange: 1, banana: 3},{apple: 2, orange: 1, banana: 3, grapes: 2},];
//Expected Result:
//{apple: 6, orange: 3, banana: 9, grapes: 3}
//NOTE: Using reduce() method

```javascript
const obj = [
    { apple: 2, orange: 1, banana: 3, grapes: 1 },
    { apple: 2, orange: 1, banana: 3 },
    { apple: 2, orange: 1, banana: 3, grapes: 2 },
];

const result = obj.reduce((acc, item) => {
    return {
        apple: acc.apple + item.apple,
        orange: acc.orange + item.orange,
        banana: acc.banana + item.banana,
        grapes: (acc.grapes || 0) + (item.grapes || 0),
    };
}, { apple: 0, orange: 0, banana: 0, grapes: 0 }); // Initial value

console.log(result);

```
## Output & Explanation
```output
{ apple: 6, orange: 3, banana: 9, grapes: 3 }
```
## 20. Flatten the nested array

```javascript

let arr=[1,3,4,[4,5,7],5,2,[[5]]];

// console.log(arr.flat(Infinity));

let newArray=[];

function flattenArray(arr){
    
    arr.map((item)=>{
        if(Array.isArray(item)){
            flattenArray(item);
        }else{
            newArray.push(item);
        }
    })
    
}

flattenArray(arr);

console.log(newArray);

```
## Output & Explanation
```output
[
  1, 3, 4, 4, 5,
  7, 5, 2, 5
]
```

## 21. let obj = [ { Sno: 1, score: 20 }, { Sno: 2, score: 30 }, { Sno: 1, score: 50 },];
// Expected [ { Sno: 1, score: 70 }, { Sno: 2, score: 30 } ]

```javascript
let obj = [
    { Sno: 1, score: 20 },
    { Sno: 2, score: 30 },
    { Sno: 1, score: 50 },
];

const result=Object.values(
    obj.reduce((acc,item)=>{
// check if Sno present in accumulator
        if(!acc[item.Sno]){ 
            acc[item.Sno]={Sno:item.Sno,score:item.score}
        }else{
// if Present then add that score with current item of score
            acc[item.Sno].score += item.score 
        }
        
        return acc;
        
    },[])
    )
    
    console.log(result)

```
## Output & Explanation
```output
[ { Sno: 1, score: 70 }, { Sno: 2, score: 30 } ]

```
