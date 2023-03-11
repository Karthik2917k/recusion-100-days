# Best Time to Buy and Sell Stock LeetCode 121

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

 

Example 1:
```
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
```
### Code
```Javascript
var maxProfit = function(prices) {
    
    let max = 0;
    let min = prices[0];
  
     for(let i = 0; i<prices.length; i++){
      
      min = Math.min(min, prices[i]);
      let current  = prices[i] - min;
      max = Math.max(current, max);
      
     }
   return max
};
```
![121](https://user-images.githubusercontent.com/96117746/224505218-7256386d-e3f5-471e-99b2-c139d68215cd.png)
