# Two Sum II - Input Array Is Sorted

- [Link to problem](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

## Solution 1

```js
var twoSum = function (numbers, target) {
  let left = 0;
  let right = numbers.length - 1; // 1

  while (left <= right) {
    // 2
    const sum = numbers[left] + numbers[right]; //3

    if (sum === target) {
      // 4
      return [left + 1, right + 1];
    } else if (sum < target) {
      // 5
      left++;
    } else if (sum > target) {
      // 5
      right--;
    }
  }
};
```

### Explanation

1. Initalize two variables to keep track of our left and right pointers
2. Create a `while` loop that runs so long as our _left_ pointer is greater than our _right_ pointer.
3. Create a `sum` variables that is sum of the numbers in the array at the left and right index.
4. If our sum is equal to our target then we can just return the answer in the format they want `[left+1, right+1]`
5. If we _do not_ have the target we can check two things. Firstly, we can check to see if the `sum < target`. Because the array is sorted in non-decreasing order (asc) we know that our sum is _smaller_ than our target. So to increase the value of sum on the next iteration we need to move our left pointer up. If `sum > target` then we know that sum is _larget_ than our target. So we need to decreased the avlue of sum on the next iteration, so we move our right pointer down.
