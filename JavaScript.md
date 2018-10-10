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
