Combination Sum III LeetCode - 216

Find all valid combinations of k numbers that sum up to n such that the following conditions are true:

Only numbers 1 through 9 are used.
Each number is used at most once.
Return a list of all possible valid combinations. The list must not contain the same combination twice, and the combinations may be returned in any order.

 

Example 1:
```
Input: k = 3, n = 7
Output: [[1,2,4]]
Explanation:
1 + 2 + 4 = 7
There are no other valid combinations.
```

## Code : 
```Javascript
var combinationSum3 = function(k, n) {
    let res = [];

    let nums = [];
    for(let i=1;i<=9;i++) nums.push(i);

    const recursive = (i,nums,k,n,arr) => {
        if(n<0) return;

        if(arr.length === k) {
            if(n===0) {
                res.push(arr.slice());
            }
            return
        }

        for(let j=i;j<nums.length;j++){
            arr.push(nums[j]);
            recursive(j+1,nums,k,n-nums[j],arr);
            arr.pop();
        }
    }

    recursive(0,nums,k,n,[]);
    return res;
};
```
![image](https://user-images.githubusercontent.com/96117746/228530010-f595157b-5ce9-4c8f-9aaa-56897242a4c7.png)
