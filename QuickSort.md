Given an array of integers nums, sort the array in ascending order and return it.

You must solve the problem without using any built-in functions in O(nlog(n)) time complexity and with the smallest space complexity possible.

Example 1:
```
Input: nums = [5,2,3,1]
Output: [1,2,3,5]
Explanation: After sorting the array, the positions of some numbers are not changed (for example, 2 and 3), while the positions of other numbers are changed (for example, 1 and 5).
```

## Code :

``` Javascript 
const pivot = (nums,left,right)=> {
    let p = right;
    let j = left;
    let i = left-1;
    while(j<=p){
        if(nums[j]<nums[p]){
            i++;
            [nums[i],nums[j]]=[nums[j],nums[i]];
            j++;
        }else{
            j++;
        }
    }
    i++;
    [nums[i],nums[p]] = [nums[p],nums[i]];
    return i;
}
var sortArray = function(nums,left=0,right=nums.length-1) {
    if(left<right){
        let pivotIndex = pivot(nums,left,right);

        sortArray(nums,left,pivotIndex-1);
        sortArray(nums,pivotIndex+1,right);
    }

    return nums;
};
```

![quicksort](https://user-images.githubusercontent.com/96117746/222725593-e2234e23-4c72-4634-876a-32da2221bc97.png)
