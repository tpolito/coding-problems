# Container With Most Water

- [Link to problem](https://leetcode.com/problems/container-with-most-water/)

## Solution 1

```js
var maxArea = function (height) {
  let l = 0, // 1
    r = height.length - 1,
    result = 0;

  // 2
  while (l <= r) {
    let area = (r - l) * Math.min(height[l], height[r]); // 3
    result = Math.max(area, result);

    //4
    if (height[l] < height[r]) {
      l += 1;
    } else {
      r -= 1;
    }
  }

  return result;
};
```

### Explanation

1. Create three variables a left pointer, right pointer (starts at length - 1), and variables to store our result.
2. Start a while loop that runs so long as the left pointer is smaller than the right pointer (ensuring they haven't crossed)
3. Calculate the area, and set the result to the largest value between its current value and the newly calculated area.
4. If the height at the left pointer is smaller then we can move it inwards by 1, and otherwise the height at the right pointer is either bigger or they are equal in which case we move the right pointer in.
