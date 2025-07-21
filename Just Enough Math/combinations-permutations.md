# Combinations and Permutations

## Permutations

- A permutation - is an arrangement of items in which the order of the items matters. For example, imagine you have three marbles, each a distinct color. How many permutations of three are there? That is, how many different ways are there to place three marbles in a row?
- Three marbles in a line. The marbles are red, blue, and green.
- There are six possible orderings of three, assuming the order of the marble colors makes a difference.
- `Ex: 3 x 2 x 1 = 6(ways)`

## Step-by-step permutations

- For example, imagine we now have five marbles, each distinctly colored, as before. How many ways are there to organize these five marbles into groups of three?
- As before, we begin by calculating the number of possible choices we have.
  `Ex: 5 x 4 x 3 = 60(ways)`

## Permutations with repetition

- What happens when we are allowed to repeat items in a permutation? Like before, we start with 26 possibilities:
  `Ex: 26 × _ × _ × _ × _ × _ = _`
- However, because we are allowed to repeat each letter as often as we like, we don't reduce the number of possibilities to 25 after the first position is filled. If we fill each of the positions with 26, we see that there are:
  `Ex: 26 × 26 x 26 x 26 x 26 x 26 = 308,915,776(possible passwords)` if we increase the length we increase the possibilities(strength) `26 × 26 × 26 × 26 × 26 × 26 × 26 = 80,331,810,176(possible passwords)`
- Using permutations, we can calculate the security levels of passwords. The more possible passwords, the better, because the higher number decreases the chance that a malicious agent gains access to sensitive information.

## Combinations

- A Combination is when we arrange a group of items such that the ordering doesn't matter

## Counting combinations

- When calculating combinations, we generally calculate the number of permutations and then remove all the "extra" arrangements by dividing. For example, in our marbles example, there are six possible permutations of the three colors:
  `Ex: 3 × 2 × 1 = 6`
- But because all six permutations contain the same three items we know that they are part of the same combination. We need to divide out the number of ways to arrange three objects from the number of permutations. First, we calculate the number of unique orderings:
  `Ex. 3 × 2 × 1 = 6`
- Which is also six. Then, we divide the number of permutations by the number of orderings:
  `Ex: 6 / 6 = 1`
- So the number of `combinations = 1`

- So now if we have 5 and can only choose 3:
  `Ex: 5 × 4 × 3 = 60`
- But because all six permutations contain the same three items we know that they are part of the same combination. We need to divide out the number of ways to arrange three objects from the number of permutations. First, we calculate the number of unique orderings:
  `Ex. 3 × 2 × 1 = 6`
- Which is also six. Then, we divide the number of permutations by the number of orderings:
  `Ex: 60 / 6 = 10`
- So the number of `combinations = 10`
