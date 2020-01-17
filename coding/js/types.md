# Types

```js
// null, undefined, boolean, number, string, object, symbol

console.log(typeof 0) // number
console.log(typeof true) // boolean
console.log(typeof 'Javascript') // "", '', `` - all of them: String
console.log(typeof undefined) // undefined
console.log(typeof Math) // or {} => object
console.log(typeof Symbol('JS')) // symbol
console.log(typeof null) // object
console.log(typeof function() {}) // function
console.log(typeof NaN) // number
```

## Type coercion

```js
let language = 'JavaScript'
if (language) {
  console.log('The best language is: ', language)
}

// '', 0, null, undefined, NaN, false
console.log(Boolean(''))
console.log(Boolean('Hello'))
console.log(Boolean(' '))
console.log(Boolean('0'))
console.log(Boolean(0))
console.log(Boolean(null))
console.log(Boolean([]))
console.log(Boolean({}))
console.log(Boolean(function() {}))
```

## Strings and numbers

```js
console.log(1 + '2') // string 12
console.log('' + 1 + 0)
console.log('' - 1 + 0)
console.log('3' * '8') // number
console.log(4 + 10 + 'px')
console.log('px' + 5 + 10) // string
console.log('42' - 40)
console.log('42px' - 2)
console.log(null + 2)
console.log(undefined + 42)
```

## Comparison operators

```js
// == vs ===
// console.log(2 == '2')
// console.log(2 === '2')
// console.log(undefined == null)
// console.log(undefined === null)
// console.log('0' == false)
// console.log('0' == 0)
// console.log(0 == 0)

// =====
console.log(false == '')
console.log(false == [])
console.log(false == {})
console.log('' == 0)
console.log('' == [])
console.log('' == {})
console.log(0 == [])
console.log(0 == {})
console.log(0 == null)
```
