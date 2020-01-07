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

## Fibonacci Sequence

```js
// For a given number of elements display fibonacci sequence
// Equation: Fn = (Fn-1) + (Fn-2)

function fib(n) {
  // solution #1: using for loop
  const result = [0, 1]

  if (n < 2) {
    return n
  }

  for (let i = 2; i <= n; i++) {
    const a = result[i - 1]
    const b = result[i - 2]

    result.push(a + b)
  }

  return result
}

console.log(fib(20))
```
