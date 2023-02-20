Given an array nums of distinct integers, return all the possible permutations. You can return the answer in any order.

Example 1:

Input: nums = [1,2,3]
Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
Example 2:

Input: nums = [0,1]
Output: [[0,1],[1,0]]
Example 3:

Input: nums = [1]
Output: [[1]]
 
Constraints:
```constraints
  1 <= nums.length <= 6
  -10 <= nums[i] <= 10
  All the integers of nums are unique.
```
code :-

```javascript
  var permute = function(nums) {
    const res = [];
    backtrack(nums, res);
    return res;
  };

  function backtrack(nums, res, n = 0) {
    if (n === nums.length - 1) {
        res.push(nums.slice(0));
        return;
    }
    for (let i = n; i < nums.length; i++) {
        [nums[i], nums[n]] = [nums[n], nums[i]];
        backtrack(nums, res, n + 1);
        [nums[i], nums[n]] = [nums[n], nums[i]];
    }
  }
```
