# Just Enough Math

## Polynomials

### Polynomial Equations(PEMDAS)

Ex. 2x + 5

- 2&5 are coefficients X is a variable and + is an operator
  - in JavaScript console.log(y - 2)

In software engineering, the most common relationship we describe is the relationship between an input size and the number of steps it takes to complete a task.

For example, imagine you are writing a program that displays the name, address, and userID for each account in an array. So, there are three pieces of information that you'll need to output for every user: name, address, and userID. If you have five users, you must output15 pieces of information in total (three pieces of information for each user). This takes 15 steps. If we let s represent the number of steps, the polynomial equation that describes this relationship is:

Ex. s = 3u
Where u equals the number of users.
So, if we are have five users, we take 3 × 5 = 15 steps to complete our job, and if we are working with 100 users, the job will take 3 × 100 = 300 steps.

### Degree of Polynomials(Exponents, Degree)

exponent -- a number written over another one indicating how many times the second number is multiplied by itself.
degree -- the size of the exponent operating on a term. In a polynomial, degree refers to the largest exponent of all the terms.

Ex. 2³ = 2 × 2 × 2 = 8

- 3 is the degree
  Many polynomials have terms with exponents. These exponents are called the degree of the term. In term 2x, the degree is just 1. This is because it contains a hidden exponent and can be equivalently written 2x¹. The exponent 1 leaves the original number the same.

Ex. x² + x
This polynomial contains two terms: x² (degree=2) and x (degree=1). Polynomial degree is the highest degree in the polynomial's terms. In the polynomial above, the polynomial degree is 2 because the term with the highest degree is x².

The higher the degree of a polynomial, the faster the rate of growth.

- Conclusion: the higher the degree the higher the runtime

### Practice

Imagine you are writing code to calculate the number of squares on different chessboards. Each chessboards is a large square consisting of equally sized small squares. Assume the size of each small square never changes.

How many squares exist on boards of different sizes, given the number of squares per side?

What is the degree of the polynomial that describes the number of steps taken to solve this problem?

- Solution:
  - b = n^2

### Conclusion

Simple construction Sq Ft math. I just need to plug in the variables and coefficients.
