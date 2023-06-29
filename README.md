# JavaScript Snippets

## Correct below JS code
```javascript
const length = 4;
const numbers = [];
for (var i = 0; i < length; i++);{
  numbers.push(i + 1);
}
console.log(numbers);
```
##Output
```output
[ 5 ]
```
## Snippet 2
```javascript
const clothes = ['jacket', 't-shirt'];
clothes.length=0;

console.log(clothes[0]);
}
```
## Snippet 3
```javascript
for (var i = 1; i <= 100; i++) {
    if (i % 15 == 0) console.log("FizzBuzz");
    else if (i % 3 == 0) console.log("Fizz");
    else if (i % 5 == 0) console.log("Buzz");
    else console.log(i);
}
```
