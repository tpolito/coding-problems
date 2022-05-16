# Product Sum

- [Link to problem](https://www.algoexpert.io/questions/Product%20Sum)

## Solution

```js
function productSum(array, depth = 1) {
  let sum = 0;

  for (const element of array) {
    if (Array.isArray(element)) {
      sum += productSum(element, depth + 1);
    } else {
      sum += element;
    }
  }

  return sum * depth;
}
```

### Explanation
