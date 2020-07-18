# PERMUTATION & COMBINATION (MATH REVIEW)

#### Permutation 

A way in which a set or number of things can be ordered or arranged (the order in this case is very important) 

* 1977 is a number with 4 digits: 1, 9, 7, 7 and the order in which they appear is important. Using the same numbers in a different order would result in something very different: 7917 

* Examples: <br>
P= permutations, n=number of things to choose from, r=the number of things chosen (*remember: factorials of 0 is equal to 1) 

    * P=n<sup>r</sup> (when repetition is allowed) an iphone password has 4 digits (the r value), each digit selection has 10 choices (0-9, the n value) and each time you select one digit you have the same 10 choices available so the permutations are (10 choices for each digit placement): 10x10x10x10 or p=104 permutations 

    * P=n! (Factorials: when repetition is not allowed) say you have to arrange the planets (8, the n value) in any order. But once you choose one planet you cannot choose that planet again (which was not the case in the prev example), so your options get smaller as you make choices (i.e. once you choose Mercury you now have 7 other planets to choose from, so the previous formula would not apply). However, you can have multiple lists with the same 5 planets in different orders (since order matters, different orders are accepted) In this case you would be looking at the first choice with 8 possibilities, the second with 7 possibilities, the third with 6 possibilities, etc so the formula would be: 8x7x6x5x4x3x2x1 or p=8! 

    * P= n!/(n-r)! (factorial with stipulations) say you have to arrange only 5 of the 8 planets. Then the formula would be p=8x7x6x5x4. To generalize the formula, you use a little fraction-trickery: multiplying the numerator and denominator of a fraction by the same number (except 0) does not affect that fraction. So you would get: p=8x7x6x5x4x3x2x1/(8-5)! OR p=8!/3! 

<hr>

#### Combinations 

A selection of items from a collection in which the order of selection does not matter 

* take coffee: it is a collection of water, sugar, coffee, and milk. However it does not matter which order you put them; it doesn’t change the combination  

* Examples: <br>
c=combinations n=number of things to choose r=number of things chosen 

    * C=n!/r!(n-r)!  (combos with no repetition) <br>
     Going back to the planets: if you can now arrange 5 of the 8 planets again however this time the order does not matter (and remember there are no repetitions). In other words: Mercury, Venus, Mars would be the same as Venus, Mercury, Mars, or Mars, Venus, Mercury (the order doesn’t matter so any group of the 3 planets is the same). How would you calculate the number of combinations you have without redundancies? To arrive at the number of combinations you would take the total of P (permutations) and divide by the total of R (redundancies) 

    * C=(n+r-1)! / (r!(n-1)!)  (combos with repetitions) <br>
    say you can choose more than 1 balloon of the same color for birthday party decorations. If the number of balloons is n and you choose r (while allowing the same color to be chosen 2x) and disregard the order of arrangement, you use this formula. 

| Operation   | Order Matters | Repetition | Formula                           |
|-------------|:-------------:|:----------:|-----------------------------------|
| Permutation |      YES      |    YES     | P(n,r) = n<sup>r</sup>            |
| Permutation |      YES      |     NO     | P(n,r) = n! / (n-r)!              |
| Combination |      NO       |     NO     | C(n,r) = n! / r!(n-1)!            |
| Combination |      NO       |    YES     | C(n+r-1, r) = (n+r-1)! / r!(n-1)! |

 