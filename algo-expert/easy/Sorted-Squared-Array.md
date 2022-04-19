# Sorted Squared array

[Link to problem](https://www.algoexpert.io/questions/Sorted%20Squared%20Array)

---

## Solution 1

```js
// O(nlogn) time | O(n) space - n is the length of the input array
function sortedSquaredArray(array) {
  // Write your code here.
  return array.map((num) => num ** 2).sort((a, z) => a - z);
}
```

### Explanation

Use `.map()` to iterate and modify each element of the input array, making use of the exponentiaion operator. This will result in an modifed input array where each number has been squared. Then we can use the built in `.sort()` method to finish the problem by sorting the array in ascending order.
