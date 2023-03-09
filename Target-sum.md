# Target Sum LeetCode-494

You are given an integer array nums and an integer target.
You want to build an expression out of nums by adding one of the symbols '+' and '-' before each integer in nums and then concatenate all the integers.
<br/>
<br/>
For example, if nums = [2, 1], you can add a '+' before 2 and a '-' before 1 and concatenate them to build the expression "+2-1"
Return the number of different expressions that you can build, which evaluates to target.

## Example

```
Input: nums = [1,1,1,1,1], target = 3
Output: 5
Explanation: There are 5 ways to assign symbols to make the sum of nums be target 3.
-1 + 1 + 1 + 1 + 1 = 3
+1 - 1 + 1 + 1 + 1 = 3
+1 + 1 - 1 + 1 + 1 = 3
+1 + 1 + 1 - 1 + 1 = 3
+1 + 1 + 1 + 1 - 1 = 3
```

## Code
```Javascript
var findTargetSumWays = function(nums, target) {
    let res= 0;
    const recursive = (i,nums,target,sum)=>{
        if(i===nums.length){
            if(sum===target) res++;
            return;
        }

        sum +=nums[i];
        recursive(i+1,nums,target,sum);
        sum -=nums[i];
        
        sum -=nums[i];
        recursive(i+1,nums,target,sum);
        sum +=nums[i];
    }
    recursive(0,nums,target,0);

    return res;

};
```

![TargetSum](https://user-images.githubusercontent.com/96117746/224013776-a6f8b547-7143-42a4-bfe7-243452bf00ac.png)
