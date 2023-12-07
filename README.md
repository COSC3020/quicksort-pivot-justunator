[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11754433&assignment_repo_type=AssignmentRepo)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

From slide 52, It suggests that $\frac{1}{2}$ of the array is a good pivot while $\frac{1}{4}$ of the front and back array each are bad pivots.
If we always pick from the left most element, we have a $\frac{1}{2}$ chance of it being good and a $\frac{2}{4}$ chance of it being bad thus 50% chance of either a good or bad pivot.
If we use the median of three method, we will be given 3 possibilites of Left, Middle, and Right elements of the array. Using the same probability of picking a good and bad pivot, we can get L = $\frac{1}{4}$, M = $\frac{1}{2}$ R = $\frac{1}{4}$ where M is the good pivot and L and R are bad pivots.
For only the bad pivot case:
$L\cdot L\cdot L$

$L\cdot L\cdot R$

$L\cdot R\cdot L$

$L\cdot R\cdot R$

$R\cdot L\cdot L$

$R\cdot L\cdot R$

$R\cdot R\cdot L$

$R\cdot R\cdot R$

There are 8 possible outcomes, each with a $\frac{1}{64}$ chance of appearing, so $\frac{1}{8}$ chance for the pivot to be strictly bad

Another bad case would be if either L or R are chosen twice and M only once:

$M\cdot L\cdot L$

$L\cdot M\cdot L$

$L\cdot L\cdot M$

$M\cdot R\cdot R$

$M\cdot R\cdot M$

$M\cdot M\cdot R$

There are 6 outcomes where this is possible which creates an outcome of $\frac{1}{32}\cdot 6$

If we combine these two bad pivot outcomes, we can get a probability of $\frac{5}{16}$ So the probability of getting a good pivot will inturn be $\frac{11}{16}$

Which is $68.75%$ of the time to be a good pivot, this is a higher probability than just picking the leftmost one every single time so this means that the median-of-three method is a better method at picking a good pivot as it has a higher chance of choosing a good pivot.
