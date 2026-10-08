# JavaScript Notes — Arrow Functions, Array Methods & Equality

## 1. Arrow Function Syntax

```javascript
const functionName = (parameters) => {
  // function body
};
```

- Shorter syntax for writing functions.
- If the body has a single expression, you can drop the `{}` and `return`:
  ```javascript
  const double = (num) => num * 2;
  ```

---

## 2. Rest Parameter

The rest parameter (`...nums`) collects any number of arguments into an array.

```javascript
const sumAll = (...nums) => {
  return nums.reduce((a, b) => a + b);
};

console.log(sumAll(1, 2, 3, 4)); // 10
```

- `...nums` gathers all passed arguments into a single array called `nums`.
- Useful when you don't know how many arguments will be passed.

---

## 3. `reduce()`

Reduces an array down to a single value by applying a function to each element, carrying forward an accumulator.

```javascript
let numbers = [1, 2, 3, 4];

// Sum all numbers
let sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 10
```

- `acc` → accumulator (running total)
- `num` → current array element
- `0` → initial value of the accumulator

---

## 4. `map()`

Creates a **new array** by transforming every element of the original array.

```javascript
let numbers = [1, 2, 3, 4];

// Using arrow function with map
let doubled = numbers.map(num => num * 7);
console.log(doubled);
// Output: [7, 14, 21, 28]
```

- Does **not** modify the original array.
- Returns a new array of the same length.

---

## 5. `filter()`

Creates a **new array** containing only the elements that pass a given condition.

```javascript
let numbers = [1, 2, 3, 4, 5, 6];

// Keep only even numbers
let evens = numbers.filter(num => num % 2 === 0);
console.log(evens); // [2, 4, 6]
```

- The callback must return `true` (keep element) or `false` (discard element).
- Returns a new array — original is unchanged.

---

## 6. Equality Operators (`==` vs `===`)

| Operator | Checks           | Example              | Result |
|----------|-------------------|-----------------------|--------|
| `==`     | Value only         | `10 == 10`             | `true` |
| `===`    | Value **and** type | `10 === 10`             | `true` |
| `===`    | Value **and** type | `10 === "10"`           | `false` (different types: number vs string) |

- `==` is the **loose equality** operator — it converts types before comparing.
- `===` is the **strict equality** operator — no type conversion; both value and type must match.
- Best practice: prefer `===` to avoid unexpected type-coercion bugs.

---

## Quick Recap Table

| Method     | Purpose                          | Returns          | Mutates Original? |
|------------|-----------------------------------|-------------------|--------------------|
| `reduce()` | Combine array into single value  | Single value      | No                |
| `map()`    | Transform each element            | New array (same length) | No          |
| `filter()` | Select elements matching condition | New array (subset) | No               |
