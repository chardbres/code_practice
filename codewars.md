# Codewars Practice

## Fundamentals

1. **(8 kyu): Summing a Number's Digits**
  * Write a function named sumDigits which takes a number as input and returns the sum of the absolute value of each of the number's decimal digits.

```js
function sumDigits(number) {
  return Math.abs(number).toString().split('').reduce((sum,num) => +sum + +num, 0)
}
```
In one line, this function makes the incoming number an absolute value, converts it to a string, and splits it between each character to make an array. Then, it uses a reduce functions to add all of the digits together: the +a, +b forces the function to treat the array as integers.
