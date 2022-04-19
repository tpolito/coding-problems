# Two Number Sum

[Link to problem](https://www.algoexpert.io/questions/Two%20Number%20Sum)

---

## Solution 1

```js
// O(n) time | O(n) space
function twoNumberSum(array, targetSum) {
  const dict = {};

  for (let num of array) {
    let potentialNum = targetSum - num;

    if (potentialNum in dict) {
      return [potentialNum, num];
    }

    dict[num] = true;
  }

  return [];
}
```

### Explanation

Create a dictonary to store the values we have tried before. Next iterate over each number in the array, and create a `potentialMatch` by taking the `targetSum` and subtracting the current number we are iterating over. With this new number we can check to see if our `potentialMatch` exists in our dictonary. If it **does** then we know we have both numbers we need to solve the problem, and we can return the `potentialMatch` along side the number we are iterating over. Otherwise, we just add the number we are checking to the dictonary to check in future iterations.
