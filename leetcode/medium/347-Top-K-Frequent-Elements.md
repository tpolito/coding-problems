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

### Explanation

1. Create a map to track the occurences of each number

- Input: `nums = [1,1,1,2,2,3], k = 2`
- Map: `{}`

2. Iterate over the array of numbers. For each number we check if that number exists as a key in the map if it does then we increment the value of that key by one. Else, we create a new key value pair in our map, where the key is the num and the value is 1.

- `{1 => 3, 2 => 2, 3 => 1}`

3. Next create an array from the keys of our map and using the `sort()` method return an array which sorts the values of the map from low -> high.

- `[1,2,3]`

4. Once we have that we can simply `splice()` from 0 to `k`

- `[1,2]`
