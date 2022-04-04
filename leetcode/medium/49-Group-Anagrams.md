# Group Anagrams

[Link to problem](https://leetcode.com/problems/group-anagrams/)

---

## Solution 1

```js
var groupAnagrams = function (strs) {
  let dict = {};

  for (const str of strs) {
    const letters = str.split('').sort().join('');

    dict[letters] ? dict[letters].push(str) : (dict[letters] = [str]);
  }

  return Object.values(dict);
};
```
