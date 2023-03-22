# Missing Number LeetCode 268

Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

Example 1:
```
Input: nums = [3,0,1]
Output: 2
Explanation: n = 3 since there are 3 numbers, so all numbers are in the range [0,3]. 2 is the missing number in the range since it does not appear in nums.
```

### Code :
```Javascript
var missingNumber = function(nums) {
    let sort = nums.sort((a,b)=>a-b);

    console.log(sort)

    for(let i=0;i<sort.length;i++){
        if(i !==sort[i]) return i
    }
    return sort.length
};
```
![image](https://user-images.githubusercontent.com/96117746/226900590-d886bd36-377d-459c-99b9-3b0a5bc034a9.png)
