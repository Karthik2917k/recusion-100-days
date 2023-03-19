# Sort the People LeetCode 2418

You are given an array of strings names, and an array heights that consists of distinct positive integers. Both arrays are of length n.

For each index i, names[i] and heights[i] denote the name and height of the ith person.

Return names sorted in descending order by the people's heights.

 

Example 1:
```
Input: names = ["Mary","John","Emma"], heights = [180,165,170]
Output: ["Mary","Emma","John"]
Explanation: Mary is the tallest, followed by Emma and John.
```

## Code : 
```Javascript
var sortPeople = function(names, heights) {
  const people = [];
  
  for(let [index, name] of names.entries()) {
    people.push([name, heights[index]]);
  }
  return people.sort((a, b) => b[1] - a[1]).map(([name]) => name);
};
```
