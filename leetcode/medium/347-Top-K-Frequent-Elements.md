# Top K Frequent Elements

[Link to problem](https://leetcode.com/problems/top-k-frequent-elements/)

---

## Solution 1

```js
var topKFrequent = function (nums, k) {
  let map = new Map();

  for (const num of nums) {
    if (!map.has(num)) {
      map.set(num, 1);
    } else {
      map.set(num, map.get(num) + 1);
    }
  }

  return Array.from(map.keys())
    .sort((a, b) => map.get(b) - map.get(a))
    .splice(0, k);
};
```
