Largest Number LeetCode - 179

Given a list of non-negative integers nums, arrange them such that they form the largest number and return it.
Since the result may be very large, so you need to return a string instead of an integer.

Example 1:
```example
Input: nums = [10,2]
Output: "210"
```

## Code :
```Javascript
  var largestNumber = function(nums) {
    let sort = nums.sort((a,b)=> {
        const ab = a.toString() + b.toString();
        const ba = b.toString() + a.toString();
        return ba-ab;
    })
    const ans = sort.join('');
    if(+ans===0) return '0';
    else return ans;
  };
```

![image](https://user-images.githubusercontent.com/96117746/221571369-ff80e8f7-c226-4230-a468-42501411db8d.png)
