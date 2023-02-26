Day-9 Word Search LeetCode - 79

Given an m x n grid of characters board and a string word, return true if word exists in the grid.

The word can be constructed from letters of sequentially adjacent cells, where adjacent cells are horizontally or vertically neighboring. The same letter cell may not be used more than once.

Example 1: 

<img src="https://assets.leetcode.com/uploads/2020/11/04/word2.jpg" alt="example1" />

```example
Input: board = [["A","B","C","E"],["S","F","C","S"],["A","D","E","E"]], word = "ABCCED"
Output: true
```

Code:

```Javascript
  var exist = function(board, word) {
    let m = board.length;
    let n = board[0].length;
    const recursion = (i,j,len) => {
        if(len === word.length) return true;
        if(i<0 || i>=m || j<0 || j>=n || board[i][j]!==word[len]) return false;
        board[i][j] = "&";
        let ans = recursion(i+1,j,len+1) || recursion(i-1,j,len+1) ||
         recursion(i,j+1,len+1) || recursion(i,j-1,len+1);
         board[i][j] = word[len];
         return ans;
    }
    let result = false;
    for(let i = 0; i<m;i++){
        for(let j=0;j<n;j++){
            result = recursion(i,j,0);
            if(result) return true;
        }
    }
    return false;
  };
```

![image](https://user-images.githubusercontent.com/96117746/221422231-f3b21e9c-9584-4793-8699-fa6f2e6c311d.png)
