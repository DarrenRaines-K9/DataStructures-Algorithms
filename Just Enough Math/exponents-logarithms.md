# Exponents and Logarithms

## Reading

In this reading, we introduce two operations that describe how certain algorithms perform: `exponents` and `logarithms`. These operations will help us choose between different algorithms.

Now, the pages to your right contain the last names beginning with a letter between T and Z, while the pages to the left contain names beginning with a letter between A and S. Because R is between A and S, you flip to the left, opening the book as close to the middle of the N–S section as you can, because you already know R was between N and Z on the first flip. You continue this task, choosing to go either left or right and subdividing the pages you need to check in half until you reach the page containing names beginning with R. Then, you start the process over for the second letter in Alejandro Rosalez's last name, "o". Eventually, you work your way through each letter in Rosalez and find Alejandro's information.

This procedure of dividing the amount of work for this task is exactly what a computer does when it searches for a specific data item in an organized list. Moving left and right, narrowing down the search space until you find the name you are looking for (or determining that the information you are looking for doesn't exist) is an effective and very efficient strategy. Without realizing, you have performed an algorithm called `binary search`.

## Binary Search

- The binary search algorithm has a smaller `growth rate` than reading through the entire directory one name at a time.

  - A `growth rate` describes how the amount of time or memory it takes to do a task changes as the size of the input increases. You can find more information about growth rates in the Polynomials reading.

## Exponents and Exponential Growth

`expression` - a sequence of numbers, symbols, and operations that can be evaluated to get a single result.

`Ex: 2 + 3`
`Ex: 2 x 4` is the same as `2 + 2 + 2 + 2`

- Exponents work according to a similar rule. Instead of adding a number repeatedly, however, an exponent tells us to multiply a number by itself repeatedly.

`Ex: 3² = 3 x 3 = 9`
`4³ = 4 x 4 x 4 = 64`

`exponent` - a number written over another one indicating how many times the second number is multiplied by itself.
`Ex: 2² = 2 x 2 = 4`

- Suppose you write a program to list all possible teams of 20 developers. That’s:
  `2²⁰ = 1,048,576 teams`

## Comparing Logarithmic and Exponential Growth

`Rule of thumb:`

- Output doubles for each input? → exponential
- Output increases slightly with input? → logarithmic
  `Note: in ATA materials and CS, log n means log₂n unless stated otherwise.`

- You’re debugging a program where binary search is done after duplicating files:

  - File count doubles every time
  - Even though search is logarithmic, duplication makes it exponential
    `After 64 runs → 2⁶⁴ = 18,446,744,073,709,551,615 files 😱`

- Suppose a list of names must be alphabetized.
  - You divide the list until pairs form, then merge pairs into sorted groups:
    `2 → 4 → 8 → 16 → ...`
  - Is this logarithmic or exponential?`Logarithmic`

## Conclusion

- In this lesson:
- `Exponents` = repeated multiplication
- `Logarithms` = finding the exponent
- `Exponential growth` = bad
- `Logarithmic growth` = good

These tools help you write efficient code. Use them wisely!
