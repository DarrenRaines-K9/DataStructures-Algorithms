## Time Complexity

- There are a few shortcuts we can use when calculating the time complexity for code. First, arithmetic operations are constant.
- Let's look at the following line of code:

```js
let sum = (8 * 4) / 3 + 9;
```

- All we're doing in this line of code are arithmetic operations, all of which are constant. So, the above line of code has `O(1)`. If we have multiple lines with `O(1)`, the overall Big O is still `O(1)`.

### For example:

```js
let num1 = 8 * 4;
let num2 = num1 / 3;
let sum = num2 + 9;
```

- The above code yields the same result as the previous line of code, just separated into three different lines. Each line is an arithmetic operation, so each line is `O(1)`. If all our lines of code are `O(1)`, then the code snippet is `O(1)`.
- Variable assignment is also constant. In the previous snippets of code, both the arithmetic operations and the variable assignment were constant. As we said previously, we can do any number of constant operations in code, and it will still have a time complexity of `O(1)`.
- Accessing elements in an array (by index) or object (by key) is also constant!

### Let's look at the following code snippet:

```js
const numArray = [4, 5, 6, 7];
const num1 = numArray[0];
```

- The code snippet initializes an array `numArray`, and then assigns the value in index `0` to a variable `num1`. This is constant because we're giving the code the index and telling it exactly where to go. This is true no matter what index we give — it's `O(1)`.
- In a loop, however, the time complexity is the length of the loop times the complexity of whatever happens in the loop.

---

## Let's look at some examples:

```js
for (let i = 0; i < numArray.length; i++) {
  console.log(numArray[i]);
}
```

### Looking at this loop:

- `n` is the length of `numArray`
- The body of the loop does constant work (`O(1)`)
- Total time: `n * 1 = n` → `O(n)`

---

### Next example with nested loops:

```js
for (let firstItem of items) {
  for (let secondItem of items) {
    console.log(firstItem + ", " + secondItem);
  }
}
```

- Outer loop runs `n` times
- Inner loop runs `n` times per outer loop
- Each print is constant → `O(1)`
- Total time: `n * n * 1 = n^2` → `O(n^2)`

### So:

- 10 items → 100 prints
- 1,000 items → 1,000,000 prints

---

### Function: Two Separate Loops

```js
function printItemsTwice(items) {
  for (let item of items) {
    console.log(item);
  }

  for (let i = 0; i < items.length; i++) {
    console.log(items[i]);
  }
}
```

- First loop → `O(n)`
- Second loop → `O(n)`
- Total: `n + n = 2n` → drop constant → `O(n)`

---

### Function: One Loop + One Nested Loop

```js
function printAllNumbersThenAllPairSums(numbers) {
  console.log("these are the numbers.");
  for (let number of numbers) {
    console.log(number);
  }

  console.log("and these are their sums.");
  for (let firstNumber of numbers) {
    for (let secondNumber of numbers) {
      console.log(firstNumber + secondNumber);
    }
  }
}
```

### Breakdown:

- First `console.log` → `O(1)`
- First loop → `O(n)`
- Nested loops → `O(n^2)`
- Total time: `O(1 + n + n^2)` → keep the most significant → `O(n^2)`
