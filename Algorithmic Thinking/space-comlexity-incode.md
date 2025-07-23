## Space Complexity

The previous examples were all about time complexity, but what about determining the space complexity of code? Determining space complexity functions very similarly to time complexity, but we're looking at the total size of any new variables we're allocating. It's important to remember that when we're talking about space complexity, we're interested in how the memory usage changes as `n` does.

---

### Example 1: Constant Space

```js
function sayHiNTimes(n) {
  for (let i = 0; i < n; i++) {
    console.log("hi");
  }
}
```

- Even though we have a loop, we're just printing out a statement. We're **not allocating any additional memory** that scales with `n`.  
  No matter what the size of `n` is, we're using the same amount of memory.  
  ✅ **Space Complexity**: `O(1)`

---

### Example 2: Linear Space

```js
function arrayOfHiNTimes(n) {
  const hiArray = [];
  for (let i = 0; i < n; i++) {
    hiArray[i] = "hi";
  }
  return hiArray;
}
```

### In the above example:

- We're creating an array the size of `n`
- The memory used **scales with `n`**

The loop doesn't use extra space itself — it just sets values. The key is that the array is **allocated in memory** to hold `n` elements.

✅ **Space Complexity**: `O(n)`

---

### Example 3: Still Constant Space

```js
function findLargestNumber(items) {
  let largest = -Infinity;

  for (let item of items) {
    if (item > largest) {
      largest = item;
    }
  }

  return largest;
}
```

## This method:

- Iterates over all values in the `items` array
- Compares each to a single variable `largest`

Even though the loop runs `n` times, **no new memory** is allocated based on the input size.  
We're just updating one variable — not storing or collecting data.

✅ **Space Complexity**: `O(1)`
