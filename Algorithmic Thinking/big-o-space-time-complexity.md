# Big-O Notation: Time vs Space Complexity

## Common Primitive Operations in Code:

| **Type**         | **Example**        | **Description**                        |
| ---------------- | ------------------ | -------------------------------------- |
| Assignment       | `x = 5`            | Store a value in memory                |
| Arithmetic       | `a + b`, `c * d`   | Add, subtract, multiply, divide        |
| Comparison       | `x === y`, `a > b` | Equality or relational check           |
| Logical ops      | `a && b`, `!flag`  | AND, OR, NOT operations                |
| Variable access  | `let z = x`        | Read the value of a variable           |
| Function call    | `print(x)`         | Call a function (with no loops inside) |
| Array access     | `arr[3]`           | Get or set a value by index            |
| Return statement | `return x + y`     | Send a result back from a function     |

- When we say something runs in O(n) or O(1), we’re really counting how many primitive operations the computer performs as input size grows.

## Big O terminology

- Okay, so we can use Big O to help us analyze our code and determine the time and space complexity of an algorithm. But what does Big O actually look like?
- Big O notation is represented in the following way: O(blah blah n blah). The 'n' represents how much data is passed into or examined in our algorithm. The 'blah blah' refers to a mathematical expression.
- The notation for Big O looks like a mathematical function call, but it's not! It's just notation for labeling the growth pattern of code. The 'O' stands for "Order of". Big O is really saying the running time/memory growth of our code grows on the 'order of' some mathematical expression of n.
- That sounds really complicated, but it's not. Let's look at a 'real world' example so we understand the terminology a bit better.

## Time complexity

- Let's say we have a big jar full of beans. Our job is to count the number of beans in the jar. In this case, the beans are our data, so the number of beans = n.
- If we're given a jar with 10 times the number of beans, it takes 10 times as long to count the beans. For example, if it takes us 10 seconds to count a jar with 10 beans, it would take us 100 seconds to count a jar with 100 beans. 10x the number of beans = 10x the amount of time!
- Therefore, counting the beans has a time complexity of O(n) (pronounced "Big O of n"). O(n) means that the time it takes to complete a task grows as n (the input data) does, or that the time growth is to the order of n.
- Now let's say the jars have labels on them that tell us how many beans are in the jar. No matter how many beans are in the jar, it takes the same amount of time for us to read the label on the jar and know how many beans are in them. This example represents O(1) (pronounced "Big O of 1", which we refer to as constant time).
- O(1) means that n (the input data) isn't involved at all
  because no matter the value of n, the runtime is the same. It takes us 1 second to read the label of the jar with 10 beans and still takes 1 second to read the label of the jar with 100 beans!
- O(1) is an ideal runtime for an algorithm. No matter how large our data is, the runtime remains the same. O(n) may be fine for smaller inputs (counting 10 beans only takes 10 seconds), but the time quickly grows as the input does (counting 10,000 beans takes 10,000 seconds, which is more than two and a half hours!).

## Space complexity

- Instead of counting beans, let's say we're sorting them into individual bags. Each bean gets taken out of the large bag and placed into an individual bag. The beans are still n, and each bag is a new variable that we're storing data in.
- This example has a space complexity of O(n) because the memory growth is to the order of n. If we have 10 beans, we need 10 bags, but if we have 100 beans, we need 100 bags. The memory used is directly related to the size of n.
- Now let's go back to counting beans. When we finish counting the beans in a jar, we write down the number on a label that we're storing. This represents a space complexity of O(1). No matter how many beans there are, the label is the same size and takes up the same amount of memory. The amount of memory used is constant and independent from the size of n.
- Just as we discussed with time complexity, O(1) is overall better for O(n) for space complexity, too. If our space complexity is dependent on the size of our input, we can run out of memory if n becomes extremely large. With a constant space complexity, we can ensure that we won't have memory issues if n becomes very large.

### Space Complexity Explained, It’s About Peak Memory, Not Total Usage

- When we analyze space complexity, we’re talking about the maximum amount of additional memory an algorithm uses at any single point during its execution — not the total memory used over time.
- This means if your algorithm creates a temporary array of size n once, the space complexity is O(n) — even if that happens multiple times or in different phases. It’s about the peak memory usage, not the cumulative memory used across all steps.

### The example below illustrates the difference between Peak Memory vs. Cumulative Memory

<pre><code class="language-js">
```js
function processArray(arr, times) {
  for (let i = 0; i < times; i++) {
    // Create a temporary array the size of the input
    let temp = arr.slice(); // O(n) space at this moment
    // Do something trivial with it, like reverse
    temp.reverse();
    // Then we drop 'temp' and move to the next iteration
  }
  return true;
}
```
</code></pre>

### 🧠 Why the space complexity is O(n), not O(n × times)

- On each iteration, the function allocates a temporary array temp of size n.
- However, as soon as one iteration finishes, temp goes out of scope and is freed up to be used by other programs.
- Memory is never used for more than one temporary array at the same time.
- Therefore, the peak temporary memory usage during execution is O(n) — no matter how many times the loop runs.
- This illustrates that space complexity measures the maximum additional memory used at any moment, not the total allocated over time.

- Also, it's important to know that space complexity excludes the input and output. For example, if a method takes an array and sorts it in place, without allocating extra memory, its space complexity is O(1) — constant space — because it's not using additional memory proportional to the input size.
  Here's a JavaScript example with an explanation that highlights how space complexity excludes input and output, and only considers additional memory used during execution:

<pre><code class="language-js">
```js
function reverseInPlace(arr) {
  let left = 0;
  let right = arr.length - 1;

  while (left < right) {
    // Swap elements
    [arr[left], arr[right]] = [arr[right], arr[left]];
    left++;
    right--;
  }

  return arr;
}
```
</code></pre>

### Space Complexity: O(1)\*

Even though this function operates on an array of size n, the space complexity is O(1) — constant space.

### Why?

- It doesn't create any new data structures that scale with the input size.
- It uses only two variables (left and right) regardless of the length of the array.
- The input array is modified in place, and no extra memory is allocated for output.

### ✅ Reminder: Space complexity does not count the input or output — only the additional memory used during execution.

## Polynomial complexity

- In the last reading, we discussed O(1) and O(n). O(1) is also known as constant, because the time/space complexity is always the same and independent from the size of n. O(n) is also known as linear, because the time/space complexity is proportional to the size of n. This causes a linear relationship between the size of n and the time/memory taken by the algorithm. The other important notation to discuss is polynomial, which is denoted as O(n^c).

### NOTE: It's common to write exponents with a ^ character. This means 52 would be written as 5^2.

- A polynomial is a type of mathematical expression comprised of variables, numbers, and operations. In algebra, we see polynomial expressions all the time, such as 4x + 2y. Another common polynomial is an exponent such as x^2 ("x squared" or "x to the 2nd power"), which is equivalent to x _ x (x times x). An exponent is really just a shortened way to write out a polynomial that multiplies the same number multiple times. x^8 is a much quicker (and neater) way to write: "x _ x _ x _ x _ x _ x _ x _ x" or "x times x times x times x times x times x times x times x".
- When we're talking about polynomial time/space complexity, we mean an algorithm that runs to the order of n^c, where n is still our input size and c is some number.
- Note: while 'n' is universally used to stand in for the size of the input, the variable used to stand in for the exponent in polynomial complexity varies. We use 'c' in this lesson, but you may also see 'k' or other letters.
- It's important to understand that polynomial complexity is just a general term for any time/space complexity where n is raised to any power. Common polynomial complexities are O(n^2) (pronounced "Big O of n squared") and O(n^3) (pronounced "Big O of n to the third or n cubed).
- But what does it actually mean for an algorithm to have a polynomial time complexity?
- Let's start by looking at O(n^2). If we write this out in its full form, it's: n _ n (n times n). This means that the time complexity it takes to run the algorithm is the input value squared. If our input is 10, then it takes 100 steps to complete the algorithm because 10 _ 10 is 100. Similarly, if we're talking about space complexity, then O(n^2) means that the amount of memory
  taken by the algorithm is equal to the input value squared. If we have a complexity of O(n^3), the complexity is the input value cubed, etc.

## How to determine Big O

- We've discussed the usefulness of Big O notation. Now, how do we apply it to actually determine what the time/space complexity for an algorithm is? There are a few steps to determining Big O for both time and space complexity.
- First, we identify which part of our code we want to analyze. This could be a whole class, but generally we're looking at a specific method or maybe even just part of a method. Maybe there's a certain loop inside a method where our code gets hung up and we want to understand why it's taking so long or running out of memory.
- Once we've identified the code that we're analyzing, we need to determine what n is. In our bean counting example, n was the beans. In the packaging example above, n was the packages. To determine what n is, think about what the input data is for our code.
- Finally, we need to count the steps in a typical run.
- What's a step? Well, there's no clear unit of measurement for Big O, so we think in terms of steps. Steps are very vague because it doesn't actually matter what a step is! When we're talking about Big O, we're looking at how the time or memory grows as n is increased. So, what a step is may change between different algorithms, but what's important is that a step remains consistent within the same algorithm, so we can see how the steps increase relative to n.
- When determining the number of steps in an algorithm, we only need to keep the most significant part in the expression. For example, if we determine the number of steps is 'n + 3', we can throw out the + 3 and say that O(n).
- Why? Well, we want to know what Big O is when n gets really large and when n is really large, we don't care about that + 3. That + 3 may matter when n is 10, but when n is a billion, it's completely overshadowed.
- What if we determine we have '3n' steps? Once again, we can throw out the '3' and just say O(n). When determining Big O, we always want to throw out any lower coefficients and just keep the biggest. So, if our algorithm has 'n^2 + n^3' we would say the algorithm has O(n^3).

### Note that this is not true for exponents that are multiplied. If your algorithm is 'n^2 _ n^3' (n squared times n cubed), this algorithm has O(n^5). This is easier to see if we replace n with a number (let's say 2), and then write out the full expression: (2 _ 2) _ (2 _ 2 \* 2). The first set of parentheses represents 2^2 and the second set represents 2^3. It's easier to see now that we could write the above expression as 2^5.
