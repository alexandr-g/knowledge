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

## Invert a binary tree in JavaScript

```js
// given a binary tree node swap its nodes values

/*
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }

      4       
   /   \      
  2     7
 / \   / \
1   3 6   9

     4
   /   \
  7     2
 / \   / \
9   6 3   1

*/

let node = {
  value: 1,
  left: {
    value: 2,
    left: {value: 4},
    right: {value: 5}
  },
  right: {
    value: 3,
    left: {value: 6},
    right: {value: 7}
  }
}

function invertTree(node) {
  if (!node) return

  let left = node.left
  let right = node.right

  node.right = left
  node.left = right
    
  invertTree(left)
  invertTree(right)

  return node
}

console.log('--->inverted tree:', invertTree(node))
```
