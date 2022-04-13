# Longest Consecutive Sequence

[Link to problem](https://leetcode.com/problems/longest-consecutive-sequence/)

---

## Solution

```js
var longestConsecutive = function (nums) {
  if (nums.length === 0) return 0; // 1
  if (nums.length === 1) return 1;

  let set = new Set(nums); // 2
  let maxSeq = 0;

  for (const num of set) {
    // 3
    if (set.has(num - 1)) continue; // 4

    let length = 1;

    while (set.has(num + length)) length += 1; // 5

    maxSeq = Math.max(length, maxSeq); // 6
  }

  return maxSeq;
};
```

### Explanation

1. Quick and easy validation
2. Create a set based on the nums array.

- We do this because retreviing a value from a set in JS is O(1), whlie something like `Array.includes` is slower.

3. Iterate over each number in our new set
4. Check to see if our current number - 1 exists in the set, if it does then we know that it **cannot** be the start of our sequence
5. Next start a while loop that runs while our number + the length of our sequence exists.
6. Compute the max between our current sequence and the length of our current longest sequence
