Subsets LeetCode (78)

Given an integer array nums of unique elements, return all possible 
subsets (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order.

Example 1:
  Input: nums = [1,2,3]
  Output: [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]

Example 2:
  Input: nums = [0]
  Output: [[],[0]]

Constraints:
```
  1 <= nums.length <= 10
  -10 <= nums[i] <= 10
  All the numbers of nums are unique.
```

## Code:-
```Javascript
var subsets = function(nums) {
    const result = [];

    const dfs = (i,nums,slate) => {
        if(i===nums.length){
            result.push(slate.slice());
            return ;
        }

        dfs(i+1,nums,slate)

        slate.push(nums[i]);
        dfs(i+1,nums,slate);
        slate.pop();
    }
    dfs(0,nums,[])
    return result;
};
```

![subsets](https://user-images.githubusercontent.com/96117746/220410889-7535150e-e24d-41b5-bd50-9a9561d3aba9.png)
