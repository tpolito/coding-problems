# Combination Sum

- [Link to problem](https://leetcode.com/problems/combination-sum/)

## Solution

```js
var combinationSum = function (candidates, target) {
  let result = [];

  function makeCombo(arr = [], sum = 0, index = 0) {
    if (sum > target) return; // 1
    else if (sum === target) result.push(arr); // 2

    // 3
    for (let i = index; i < candidates.length; i++) {
      makeCombo([...arr, candidates[i]], sum + candidates[i], i);
    }
  }

  makeCombo();

  return result;
};
```

### Explanation

We make use of a recursive solution. Initialiing a `result` array to store our solution in.
