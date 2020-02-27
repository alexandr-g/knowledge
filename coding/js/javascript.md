# JavaScript

## Links

- [Design Patterns](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#designpatternstructure)
- [Eloquent javascript](https://eloquentjavascript.net/02_program_structure.html)
- [JS the right way](http://jstherightway.org/)

## Cheat sheet

### Objects

```js
const object = {
  a: 'somestring',
  b: 42,
  c: false
}
```

[Object.keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys) - returns an array with object keys.

```js
Object.keys(object) => ["a", "b", "c"]
```

[Object.values()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values) - returns an array of object values, omit keys.

```js
Object.values(object) => ["somestring", 42, false]
```

[Object.entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) - returns an array with `[key, value]` pairs.

```js
for (let [key, value] of Object.entries(object)) {
  console.log(`${key}: ${value}`)
}

// expected output:
// "a: somestring"
// "b: 42"
// order is not guaranteed
```

[Object.freeze()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze) - prevent object mutations.

### console.log() with css styles

```js
console.log('%cyou are awesome :)', 'color: white; font-size: 46px')
```
