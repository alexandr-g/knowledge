# Coding Exercises

## Reverse a string

```js
// Given a string, return a new string with the reversed order of characters.

function reverse(str) {
  // solution #1: using .reverse() helper

  // String.prototype.split() : String = () -> ['', '']
  // Array.prototype.reverse() : [] -> []
  // Array.prototype.join() : [] -> String

  return str
    .split('')
    .reverse()
    .join('')

  // solution #2: using for...of loop

  let reversed = ''

  for (let character of str) {
    reversed = character + reversed
  }

  return reversed

  // solution #3: using reduce()

  return str.split('').reduce((rev, char) => char + rev, '')
}
```
