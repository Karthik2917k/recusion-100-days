Write a program to solve a Sudoku puzzle by filling the empty cells.

A sudoku solution must satisfy all of the following rules:

Each of the digits 1-9 must occur exactly once in each row.
Each of the digits 1-9 must occur exactly once in each column.
Each of the digits 1-9 must occur exactly once in each of the 9 3x3 sub-boxes of the grid.
The '.' character indicates empty cells.

 

Example 1:

```
Input: board = [["5","3",".",".","7",".",".",".","."],["6",".",".","1","9","5",".",".","."],[".","9","8",".",".",".",".","6","."],["8",".",".",".","6",".",".",".","3"],["4",".",".","8",".","3",".",".","1"],["7",".",".",".","2",".",".",".","6"],[".","6",".",".",".",".","2","8","."],[".",".",".","4","1","9",".",".","5"],[".",".",".",".","8",".",".","7","9"]]
Output: [["5","3","4","6","7","8","9","1","2"],["6","7","2","1","9","5","3","4","8"],["1","9","8","3","4","2","5","6","7"],["8","5","9","7","6","1","4","2","3"],["4","2","6","8","5","3","7","9","1"],["7","1","3","9","2","4","8","5","6"],["9","6","1","5","3","7","2","8","4"],["2","8","7","4","1","9","6","3","5"],["3","4","5","2","8","6","1","7","9"]]
Explanation: The input board is shown above and the only valid solution is shown below:
```

### Code

```Javascript

function solveSudoku(board) {
  const n = board.length;
  dfs(board, n);
}

function dfs(board, n) {
  for (let row = 0; row < n; row++) {
    for (let col = 0; col < n; col++) {
      
      if (board[row][col] !== '.') continue;
     
      for (let i = 1; i <= 9; i++) {
        const c = i.toString();
       
        if (isValid(board, row, col, n, c)) {
          board[row][col] = c;
         
          if (dfs(board, n)) return true;
        }
      }
      
      board[row][col] = '.';
      
      return false;
    }
  }
  
  return true;
}

function isValid(board, row, col, n, c) {
  const blockRow = Math.floor(row / 3) * 3;
  const blockCol = Math.floor(col / 3) * 3;
  for (let i = 0; i < n; i++) {
    if (board[row][i] === c || board[i][col] === c) return false;
    const curRow = blockRow +  Math.floor(i / 3);
    const curCol = blockCol +  Math.floor(i % 3);
    if (board[curRow][curCol] === c) return false;
  }
  return true;
}

```
![sudoku solver](https://user-images.githubusercontent.com/96117746/222154362-7d416ae0-edaa-4345-907c-a3b49cc3bcd9.png)

 
