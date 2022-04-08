# Valid Sudoku

[Link to problem](https://leetcode.com/problems/valid-sudoku/)

---

```js
var isValidSudoku = function (board) {
  for (let r = 0; r < 9; r += 1) {
    let row = new Set(),
      col = new Set(),
      square = new Set();
    for (let c = 0; c < 9; c += 1) {
      let rowVal = board[r][c];
      let colVal = board[c][r];
      let squareVal =
        board[3 * Math.floor(r / 3) + Math.floor(c / 3)][
          ((3 * r) % 3) + (c % 3)
        ];

      if (rowVal === '.' || colVal === '.' || squareVal === '.') continue;

      if (row.has(rowVal)) return false;
      if (col.has(colVal)) return false;
      if (square.has(squareVal)) return false;

      row.add(rowVal);
      col.add(colVal);
      square.add(squareVal);
    }
  }

  return true;
};
```

### Explanation
