Permutations II - (LeetCode 47)

Given a collection of numbers, nums, that might contain duplicates, return all possible unique permutations in any order.

Example 1:
Input: nums = [1,1,2]
Output: [[1,1,2],[1,2,1],[2,1,1]]

Example 2:
Input: nums = [1,2,3]
Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]

Constraints:
```
1 <= nums.length <= 8
-10 <= nums[i] <= 10
```
## code

```javascript
var permuteUnique = function(nums) {
    const result = [];
    const dfs = (i,nums) => {
        if(i===nums.length-1){
            result.push(nums.slice());
            return;
        }
        let obj = {};
        for(let j=i;j<nums.length;j++){
            if(obj[nums[j]]) continue;
            obj[nums[j]] = true;
            let temp = [...nums];
            [temp[i],temp[j]]=[temp[j],temp[i]];
            dfs(i+1,temp);
        }
    }  
    dfs(0,nums);
    return result;
};
```

![permutation](https://user-images.githubusercontent.com/96117746/220411181-57d5ad3d-6639-48c3-86d7-19c0f1f00359.png)

