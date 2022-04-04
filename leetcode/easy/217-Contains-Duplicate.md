# Contains Duplicate

[Link to problem](https://leetcode.com/problems/contains-duplicate/)

---

## Solution 1

```js
var containsDuplicate = function (nums) {
  for (const num of nums) {
    if (nums.indexOf(num) !== nums.lastIndexOf(num)) return true;
  }

  return false;
};
```
