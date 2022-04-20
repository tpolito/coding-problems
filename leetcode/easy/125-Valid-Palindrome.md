# Valid Palindrome

[Link to problem](https://leetcode.com/problems/valid-palindrome/)

---

## Solution 1

```js
var isPalindrome = function (s) {
  let newString = s.replace(/[^0-9a-z]/gi, '').toLowerCase();

  return newString === newString.split('').reverse().join('');
};
```

### Explanation

1. Create new string by removing all _non_ letters/numbers and converting the entire string to lower case.
2. Check if the cleaned string is equal to the cleaned string reversed.

## Solution 2

```js
var isPalindrome = function (s) {
  let newString = s.replace(/[^0-9a-z]/gi, '').toLowerCase();
  let reverse = '';

  for (let letter of newString) {
    reverse = letter + reverse;
  }

  return newString === reverse;
};
```

### Explanation

Same as **Solution 1**, but we reverse the string manually instead of using built in functions.
