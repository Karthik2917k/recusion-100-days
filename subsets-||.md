5 - Subsets II LeetCode - (90)
Given an integer array nums that may contain duplicates, return all possible subsets
The solution set must not contain duplicate subsets. Return the solution in any order.

Example 1:

Input: nums = [1,2,2]
Output: [[],[1],[1,2],[1,2,2],[2],[2,2]]
Example 2:

Input: nums = [0]
Output: [[],[0]]

Constraints:
```javascript
  1 <= nums.length <= 10
  -10 <= nums[i] <= 10
```
### Code:

```javascript
  var subsetsWithDup = function(nums) {
    let arr=[]
    nums.sort((e1,e2)=>e1-e2)
    const subSet=(nums,index,set)=>{
          if(index>=nums.length){
                   arr.push(set)
              return
          }
                subSet(nums,index+1,[...set,nums[index]])
                while(nums[index]==nums[index+1]) index++
                subSet(nums,index+1,set)
    }
    subSet(nums,0,[])
    return arr
  };

```

