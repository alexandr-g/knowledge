# BASICS

## Variables

```ts
/**
 * (1) x is a string, b/c we’ve initialized it
 */
let x = 'hello world'

/**
 * (2) reassignment is fine
 */
x = 'hello mars'

/**
 * (3) but if we try to change type
 */
x = 42 // 🚨 ERROR

/**
 * (4) let's look at const. The type is literally 'hello world'
 */
const y = 'hello world'

/**
 * This is called a 'string literal type'. y can never be reassigned since it's a const,
 * so we can regard it as only ever holding a value that's literally the string 'hello world'
 * and no other possible value
 */
```

### Reference

All the code examples are coming from [Mike's TypeScript Fundamentals Course](https://github.com/mike-works/typescript-fundamentals)
