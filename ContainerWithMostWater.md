# Container With Most Water LeetCode 11

You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.

 ![image](https://user-images.githubusercontent.com/96117746/229323734-c54fbdbe-f4e8-4b5d-b15d-7c22cc1dbc70.png)

Example 1:

```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

### Code :
```Javascript
var maxArea = function(height) {
    let ans = 0, i = 0, j = height.length-1
    while (i < j) {
        ans = Math.max(ans, Math.min(height[i], height[j]) * (j - i))
        height[i] <= height[j] ? i++ : j--
    }
    return ans
};
```

![11](https://user-images.githubusercontent.com/96117746/229323773-232dd043-6367-4036-9084-8f2a4655807b.png)
