The coin changing problem is, given a value $v$ and a set of $n$ coins $\{c_1,c_2,...,c_n\}$ how do we calculate the smallest collection of coins possible that sum to that value. We can assume there are an infinite number of each coin.

# Greedy solution
The most obvious solution, is to simply take the largest coin that is smaller than the remaining change and repeat until there is no more change required.

This works in a lot of cases, however is not generalisable to all coin systems, for example if we have coins of value 1, 5, 7 then the greedy solution would suggest that we should use 7+7+1+1+1+1 to represent 18, even though the actual best solution is to use 7+5+5+1.

# Dynamic programming solution
The correct solution is to calculate all possible combinations of 2 coins, and store 