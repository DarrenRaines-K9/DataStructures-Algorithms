# Combinations and Permutations

## Reading

- You are a member of a team of eight developers who frequently pair up to collaborate. Figure 1 below shows one possible arrangement of pairings:

## Permutations

- A permutation - is an arrangement of items in which the order of the items matters. For example, imagine you have three marbles, each a distinct color. How many permutations of three are there? That is, how many different ways are there to place three marbles in a row?
- Three marbles in a line. The marbles are red, blue, and green.
- There are six possible orderings of three, assuming the order of the marble colors makes a difference.
  `Ex: 3 x 2 x 1 = 6(ways)`

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

## Step-by-step combinations

Let's return to our introductory example. Your manager now asks you to write a program that will print every possible pair for collaborating (not pair programming). How many pairs of eight developers are there? Remember that order doesn't matter when you're just paired off for collaborating

- First, we calculate the number of permutations:
  `8 × 7 = 56`
- Then, we calculate the number of ways to arrange two people in a pair:
  `2 × 1 = 2`
- Finally, we divide the number of permutations by the number of ways two people can be paired:
  `56 / 2 = 28`

## I Do

- Let's review our understanding of combinations and permutations by exploring a few examples. Imagine you plan a garden. You can plant roses, pansies, tulips, violets, snapdragons, and poppies. However, your garden is only wide enough to allow four plants to grow side-by-side. How many ways are there to order your flowers?
  - In this problem, we know we deal with a permutation because the arrangement of the four flowers matters. We begin with an empty garden plot with four empty spots:
    `_ × _ × _ × _`
  - In the first spot, there are six possible flowers:
    `6 × _ × _ × _`
  - We can plant one of five possible flowers in the second slot:
    `6 × 5 × _ × _`
  - And in the last two slots we can plant one of four and three possible flowers, respectively:
    `6 × 5 × 4 × 3 = 360(permutations)`
  - Multiplying all the possibilities together, we see that there are 360 ways to arrange the six flowers across four spaces.
  - What if order doesn't matter? That is, how many combinations are there? We know that there are 360 permutations, so all we need to do is calculate the number of ways to arrange four objects:
    `4 × 3 × 2 × 1 = 24(possibilities)`
  - Then, we divide 360 by 24:
    `360 / 24 = 15(combinations)`

## You Do

- Suppose a customer places an order for seven packages before leaving on a one-week vacation. When the customer returns, five of the seven packages have been delivered. How many possible ways are there for five of seven packages to arrive? Is this number larger or smaller than the number of ways five out of seven packages could be delivered if the arrival order was important?

  - In this problem we know we have a permutation because only 5 packages arrived:
    `_ x _ x _ x _ x _`
  - In the first spot there are 7 possible options of the package that arrived
    `7 x 6 x 5 x 4 x 3 = 2,520(permutations)`
  - Only 5 arrived so we need the number of possibilities
    `5 x 4 x 3 x 2 x 1 = 120(possibilities)`
  - Now we need to divide in order to get the possible ways the mail came(combinations)
    `2520 / 120 = 21(combinations)`
