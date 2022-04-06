# Group Anagrams

[Link to problem](https://leetcode.com/problems/group-anagrams/)

---

## Solution 1

```js
var groupAnagrams = function (strs) {
  if (strs.length === 0) return [];
  if (strs.length === 1) return [strs];

  let dict = {};

  for (const str of strs) {
    const letters = str.split('').sort().join('');

    dict[letters] ? dict[letters].push(str) : (dict[letters] = [str]);
  }

  return Object.values(dict);
};
```

### Explanation

Initial validation. Then we create an object to store the known anagrams in. Next we iterate over each string in our input array. For each string, we get the letters present by sorting the curent string we are iterating over. Next we check if our object has a key that matches our sorted letters. If it _does_ we can just push our current sting into that array. Else we create an array containing our current string. We can finally use `Object.values()` which returns an array containing all the values on a object, to return the answer array.
