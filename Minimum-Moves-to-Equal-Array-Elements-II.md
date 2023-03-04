Minimum Moves to Equal Array Elements II

Given an integer array nums of size n, return the minimum number of moves required to make all array elements equal.

In one move, you can increment or decrement an element of the array by 1.

Test cases are designed so that the answer will fit in a 32-bit integer.

 Example 1:
```
Input: nums = [1,2,3]
Output: 2
Explanation:
Only two moves are needed (remember each move increments or decrements one element):
[1,2,3]  =>  [2,2,3]  =>  [2,2,2]
```
Code: 
```Javascript
var minMoves2 = function(nums) {
    nums.sort((a,b)=> a-b);
    let low =0, high=nums.length-1, res =0;
    while(low<high){
        console.log(res)
        res+= nums[high]-nums[low];
        low++;
        high--;
        console.log(res)
    }
    return res;
};
```
![image](https://user-images.githubusercontent.com/96117746/222924468-a253740e-5441-4c8d-880d-cf362de698bb.png)
