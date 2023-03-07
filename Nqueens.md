N-Queens - LeetCode - 20

The n-queens puzzle is the problem of placing n queens on an n x n chessboard such that no two queens attack each other.

Given an integer n, return all distinct solutions to the n-queens puzzle. You may return the answer in any order.

Each solution contains a distinct board configuration of the n-queens' placement, where 'Q' and '.' both indicate a queen and an empty space, respectively.

Example
```
Input: n = 4
Output: [[".Q..","...Q","Q...","..Q."],["..Q.","Q...","...Q",".Q.."]]
```
# Code : 
```JavaScript
  const formatBoard = (board) => {
    let result = [];
    for(let col=0;col<board.length;col++){
        let newRow = Array(board.length).fill('.');
        newRow[board[col]] = "Q";
        result.push(newRow.join(""));
    }
    return result;
}
var solveNQueens = function(n) {
    const res = [];
    const recursive = (i,n,arr) => {
        let lQueen = i-1;
        for(let pQueen=0;pQueen<lQueen;pQueen++){
            if(arr[pQueen]===arr[lQueen]) return;
            let rowDifference = Math.abs(pQueen-lQueen);
            let colDifference = Math.abs(arr[pQueen]-arr[lQueen]);
            if(rowDifference===colDifference) return 
        }

        if(i===n){
            res.push(arr.slice());
            return;
        }

        for(let col=0;col<n;col++){
            arr.push(col);
            recursive(i+1,n,arr);
            arr.pop();
        }
    }
    recursive(0,n,[]);
    return res.map(board=>formatBoard(board));
};
```

![nqueen](https://user-images.githubusercontent.com/96117746/223417905-0cf8fffe-e782-49ed-83e8-e02014ffcda7.png)
