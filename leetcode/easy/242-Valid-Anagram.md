# Valid Anagram

[Link to problem](https://leetcode.com/problems/valid-anagram/)

---

## Solution 1

```js
var isAnagram = function (s, t) {
  return s.split('').sort().join() === t.split('').sort().join();
};
```
