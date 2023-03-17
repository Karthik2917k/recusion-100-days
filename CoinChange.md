# Coin Change LeetCode 322

You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.
Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.
You may assume that you have an infinite number of each kind of coin.

 

Example 1:
```
Input: coins = [1,2,5], amount = 11
Output: 3
Explanation: 11 = 5 + 5 + 1
```

# Code : 

```JavaScript
var coinChange = function(coins, amount) {
    const count = new Array(amount + 1).fill(Infinity)
    count[0] = 0
    for(const currentCoin of coins){
        for(let currentAmount = currentCoin; currentAmount <= amount; currentAmount++){
            count[currentAmount] = Math.min(count[currentAmount],
            count[currentAmount - currentCoin] + 1)
        }
    }
    return count[amount] == Infinity ? -1 : count[amount]
};
```

