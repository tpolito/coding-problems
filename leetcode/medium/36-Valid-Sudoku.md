# Valid Sudoku

[Link to problem](https://leetcode.com/problems/valid-sudoku/)

---

## Solution 1

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

---

## Solution 2

```js
var isValidSudoku = function (board) {
  let checked = new Set();

  for (let i = 0; i < 9; i++) {
    for (let j = 0; j < 9; j++) {
      let cell = board[i][j];

      if (cell != '.') {
        let row = `r${i}${cell}`;
        let col = `c${j}${cell}`;
        let adjacent = `s${Math.floor(i / 3)}${Math.floor(
          parseInt(j / 3)
        )}${cell}`;

        if (!checked.has(col) && !checked.has(row) && !checked.has(adjacent)) {
          checked.add(col);
          checked.add(row);
          checked.add(adjacent);
        } else {
          return false;
        }
      }
    }
  }
  return true;
};
```
