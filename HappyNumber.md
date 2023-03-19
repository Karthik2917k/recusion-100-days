# Happy Number LeetCode 202
 
Write an algorithm to determine if a number n is happy.

A happy number is a number defined by the following process:

Starting with any positive integer, replace the number by the sum of the squares of its digits.
Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
Those numbers for which this process ends in 1 are happy.
Return true if n is a happy number, and false if not.

 

Example 1:
```
Input: n = 19
Output: true
Explanation:
12 + 92 = 82
82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1
```

## Code : 
```Javascript
const Value = (n) => {
    let total = 0;
    while(n !== 0){
        let lastDigit = n%10;
        n = Math.floor(n/10);
        total += Math.pow(lastDigit,2)
    }

    return total;
}

var isHappy = function(n) {
    let fast = n;
    let slow = n;

    while(true){
        fast = Value(Value(fast));
        slow = Value(slow);

        if(fast === slow){
            return fast===1
        }
    }
};
```
![image](https://user-images.githubusercontent.com/96117746/226189576-1989898f-19fd-4997-b124-ab2b70d5e86d.png)
