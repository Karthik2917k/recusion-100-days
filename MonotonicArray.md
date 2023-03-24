# Monotonic Array LeetCode 896

An array is monotonic if it is either monotone increasing or monotone decreasing.

An array nums is monotone increasing if for all i <= j, nums[i] <= nums[j]. An array nums is monotone decreasing if for all i <= j, nums[i] >= nums[j].

Given an integer array nums, return true if the given array is monotonic, or false otherwise.

 

Example 1:
```
Input: nums = [1,2,2,3]
Output: true
```
Example 2:
```
Input: nums = [6,5,4,4]
Output: true
```

## Code :
```Javascript
var isMonotonic = function(nums) {
    let inc = null
  for (let i = 0; i < nums.length - 1; i++) {
    const num = nums[i]
    if (nums[i] < nums[i + 1]) {
      if (inc == 0) return false
      inc = 1
    } else if (nums[i] > nums[i + 1]) {
      if (inc == 1) return false
      inc = 0
    }
  }
  return true
};
```

![896](https://user-images.githubusercontent.com/96117746/227450227-88ce3b1e-1774-42c1-a0ba-a1b5b52678d6.png)
