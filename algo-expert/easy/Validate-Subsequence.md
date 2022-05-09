# Validate Subsequence

- [Link to problem](https://www.algoexpert.io/questions/Validate%20Subsequence)

## Solution

```js
function isValidSubsequence(array, sequence) {
  let index = 0;

  for (let num of array) {
    if (num === sequence[index]) {
      index += 1;
    }
  }

  return index === sequence.length;
}
```

### Explanation

Create a variable to track the index of the sequence we are checking. Next we iterate over the array of numbers, and at each index we check to see if the number at that index is equal to the number in the sequence at our tracked index. If it is we can increase the index variable by one. To find our solution we can check if the index is the same length as a the sequence. Meaning that every item in the sequence is present in the array.
