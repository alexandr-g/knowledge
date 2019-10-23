# Coding Exercises

## Reverse a string

```js
// Given a string, return a new string with the reversed order of characters.

function reverse(str) {
  // solution 1

  // String.prototype.split() : String = () -> ['', '']
  // Array.prototype.reverse() : [] -> []
  // Array.prototype.join() : [] -> String

  return str
    .split('')
    .reverse()
    .join('')
}
```
