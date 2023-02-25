Letter Combinations of a Phone Number   LeetCode - 17

Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent. Return the answer in any order. A mapping of digits to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters

<img src="https://assets.leetcode.com/uploads/2022/03/15/1200px-telephone-keypad2svg.png" alt="/" />

Example 1:


Input: digits = "23"
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]

Code: 

```Javascript
  var letterCombinations = function(digits) {
    if(digits.length<1) return [];
    const ans = [];
    const letters = {
        '2':'abc',
        '3':'def','4':'ghi','5':'jkl','6':'mno','7':'pqrs','8':'tuv','9':'wxyz'
    }

    const recursive = (i,digits,arr) => {
        if(i === digits.length){
            ans.push(arr.join(''));
            return;
        }

        const chars = letters[digits[i]];

        for(let char of chars) {
            arr.push(char);
            recursive(i+1,digits,arr);
            arr.pop();
        }
    }

    recursive(0,digits,[]);
    return ans;
};
```
![mobile](https://user-images.githubusercontent.com/96117746/221367318-96228356-fb69-4460-a8e1-aa60536f01e0.png)
