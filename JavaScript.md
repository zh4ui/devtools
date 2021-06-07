# Idiomatic JavaScript

## Expressions

### undefined or null

```js
// safely extract a propertiy value from an object, gets undefined if obj is not valid or obj has no propname
let prop = obj && obj[propName]
```

```js
// call func on prop if func is valid, and use the result returned by func as the value. Otherwise just use prop as the value.
let value = func ? func(prop) : prop
```

## Surprings!

### const

`const` only makes the name of a variable stay constant, but not its value:

```js
const x = []
x.push("hi")
console.log(x) // outputs ["hi"]

x = 1 // TypeError: Assignment to constant variable.
const x = 2 // SyntaxError: Identifier 'x' has already been declared
```

### ES2017 String.prototype.padStart

```js
const zeroPad = (num, places) => String(num).padStart(places, '0')

console.log(zeroPad(5, 2)); // "05"
console.log(zeroPad(5, 4)); // "0005"
console.log(zeroPad(5, 6)); // "000005"
console.log(zeroPad(1234, 2)); // "1234"
```

[How to output numbers with leading zeros in JavaScript? [duplicate]](https://stackoverflow.com/questions/2998784/how-to-output-numbers-with-leading-zeros-in-javascript)

## Yarn

**yarn cache**

* `yarn cache list`
* `yarn cache clean`

