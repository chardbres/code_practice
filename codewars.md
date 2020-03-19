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

2. **(6 kyu): Array.diff**
  * Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result. It should remove all values from list ```a```, which are present in list ```b```.

```js
function array_diff(a, b) {
  diff = a.filter(x => !b.includes(x))
  return diff
}
```
```ruby
def array_diff(a, b)
  a.select { |x| !b.include?(x) }
end
```

The answers are self-evident.

3. **(6 kyu): Duplicate Encoder**
  * The goal of this exercise is to convert a string to a new string where each character in the new string is ```"("``` if that character appears only once in the original string, or ```")"``` if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.

```js
function duplicateEncode(word){
  return word
    .toLowerCase()
    .split('')
    .map( function (a, i, w) {
      return w.indexOf(a) == w.lastIndexOf(a) ? '(' : ')'
    })
    .join('');
}
```
The solution takes the incoming word, casts it all in lower case, then splits it into an array of each character. Then, it maps the parens to a new array, depending on whether the item ```a``` has appeared in array ```w``` before.

4. **(5kyu): RGB to Hex Conversion**
  ```js
  function rgb(r, g, b){
    return toHex(r)+toHex(g)+toHex(b);
  }

  function toHex(d) {
      if(d < 0 ) {return "00";}
      if(d > 255 ) {return "FF";}
      return  ("0"+(Number(d).toString(16))).slice(-2).toUpper
  ```

  5. **(5kyu): Return URL from domain name**
  ```js
  function domainName(url){
    console.log(url)

    if (url.includes('www')) {
      return url.split('.')[1]
    } else if (url.includes('//')) {
      return url.split('//')[1].split('.')[0]
    } else {
      return url.split('.')[0]
    }
  }
  ```

  6. **(5kyu): Josephus Survivor**
  ```js
  function josephusSurvivor(n,k){
    let counter = k
    let josArray = [...Array(n).keys()].map(e => e + 1)
    while(josArray.length > 1) {
      let tempArray = []

      while (counter > josArray.length) {
        counter = counter - josArray.length
      }

      tempArray.push(josArray.slice(counter))
      tempArray.push(josArray.slice(0,counter-1))
      josArray = tempArray.reduce((a,b) => a.concat(b))
      counter = k
    }
    return josArray[0]
  }
  ```
