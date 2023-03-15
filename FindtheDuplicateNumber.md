# Find the Duplicate Number LeetCode 287

Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.

There is only one repeated number in nums, return this repeated number.

You must solve the problem without modifying the array nums and uses only constant extra space.

 

Example 1:
```
Input: nums = [1,3,4,2,2]
Output: 2
```

## Code :
```Javascript
  var findDuplicate = function(nums) {
    let obj = {};
    for(let num of nums) {
        if(obj[num]===undefined){
            obj[num]=1;
        }else{
            return num
        }
    }
};
```

![287](https://user-images.githubusercontent.com/96117746/225305551-f3336de2-340e-4a68-96f8-73b74e731250.png)
