#  Find All Duplicates in an Array Leetcode 442

Given an integer array nums of length n where all the integers of nums are in the range [1, n] and each integer appears once or twice, return an array of all the integers that appears twice.

You must write an algorithm that runs in O(n) time and uses only constant extra space.

Example 1:
```
Input: nums = [4,3,2,7,8,2,3,1]
Output: [2,3]
```
### Code :
```Javascript
var findDuplicates = function(nums) {
    let obj = {};
    for(let i of nums){
        if(obj[i]==undefined){
            obj[i]=1;
        }else{
            obj[i]++;
        }
    }
    console.log(obj);
    let res =[];
    for(let i in obj){
        if(obj[i]>1){
            res.push(i);
        }
    }
    return res;
};
```
![image](https://user-images.githubusercontent.com/96117746/224308621-be661c6f-9e12-4ca3-b91d-edc1be6e61d1.png)
