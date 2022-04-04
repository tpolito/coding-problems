# Two Sum

[Link to problem](https://leetcode.com/problems/two-sum/)

---

## Solution 1

```js
var twoSum = function (nums, target) {
  let d = {};

  for (let i = 0; i < nums.length; i += 1) {
    let potentialMatch = target - nums[i];

    if (potentialMatch in d) {
      return [d[potentialMatch], i];
    } else {
      d[nums[i]] = i;
    }
  }
};
```
