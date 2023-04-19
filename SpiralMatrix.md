# Spiral Matrix  LeetCode 54

Given an m x n matrix, return all elements of the matrix in spiral order.
  
Example
<img src="https://assets.leetcode.com/uploads/2020/11/13/spiral1.jpg" />
```
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [1,2,3,6,9,8,7,4,5]
```

### Code 

```Javascript 

/**
 * @param {number[][]} matrix
 * @return {number[]}
 */
var spiralOrder = function(matrix) {
    // l = Left
    // t = Top
    // r = Right
    // b = Bottom
    let ans = [],n = matrix.length,count=0;
    let size = n* matrix[0].length;
    let l=0,t=0,b= matrix.length-1,r = matrix[0].length-1;
while(count<size){

    for(let i=l;i<=r && count<size;i++){
        ans.push(matrix[t][i]);
        count++;
    }
    t++;
     for(let i=t;i<=b && count<size;i++){
        ans.push(matrix[i][r]);
        count++;
    }
    r--;
     for(let i=r;i>=l && count<size;i--){
        ans.push(matrix[b][i]);
        count++;
    }
    b--
     for(let i=b;i>=t && count<size;i--){
        ans.push(matrix[i][l]);
        count++;
    }
    l++;
}
    console.log(ans)
    return ans
};


```
