# Find First and Last Position of Element in Sorted Array LeetCode 34

Given an array of integers nums sorted in non-decreasing order, find the starting and ending position of a given target value.

If target is not found in the array, return [-1, -1].

You must write an algorithm with O(log n) runtime complexity.

 

Example 1:
```
Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```
Example 2:
```
Input: nums = [5,7,7,8,8,10], target = 6
Output: [-1,-1]
```

### Code : 
```Javascript
var searchRange = function(nums, target) {
    if(nums.length === 0) return [-1,-1]
    let start,last;

    for(let i=0;i<nums.length;i++){
        if(nums[i]===target){
            start = i;
            break;
        }
    }
    if(start===undefined) return [-1,-1]
     for(let i=0;i<nums.length;i++){
        if(nums[i]===target){
            last = i;
        }
    }
    return [start,last]
};
```
![34](https://user-images.githubusercontent.com/96117746/229324130-2daf1d6e-f626-43f7-88d6-3a5feb9eb35d.png)
