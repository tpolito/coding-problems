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
        board[3 * Math.floor(r / 3) + Math.floor(c / 3)][(r % 3) * 3 + (c % 3)];

      if (row.has(rowVal) || col.has(colVal) || square.has(squareVal))
        return false;

      if (rowVal !== '.') row.add(rowVal);
      if (colVal !== '.') col.add(colVal);
      if (squareVal !== '.') square.add(squareVal);
    }
  }

  return true;
};
```

### Explanation
