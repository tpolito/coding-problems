# Product of Array Except Self

- [Link to problem](https://leetcode.com/problems/product-of-array-except-self/)
  - [Fantastic explanation](<https://leetcode.com/problems/product-of-array-except-self/discuss/694266/Javascript-Solution-(No-Division)-(With-Explanation)>)

## Solution 1

```js
var productExceptSelf = function (nums) {
  let len = nums.length;
  let leftNums = [],
    leftMultiplier = 1;
  let rightNums = [],
    rightMultiplier = 1;

  for (let i = 0; i < len; i += 1) {
    leftNums[i] = leftMultiplier;
    leftMultiplier *= nums[i];
  }

  for (let j = len - 1; j >= 0; j -= 1) {
    rightNums[j] = rightMultiplier;
    rightMultiplier *= nums[j];

    rightNums[j] *= leftNums[j];
  }

  return rightNums;
};
```

### Explanation

![Example Image](../../imgs/238-product-of-array-except-self.png)

1. Create one array with incremental multiplication starting from the left and other starting from the right. The first element in each array will be `1` because we have no multiplication prior to it.
2. After performing both iterations, in the left array we will have the mutiples of the left elements prior to that index and in the right array we will have the multiples of all the elements to the right of that index.
3. By multiplying the index of each array, we can calcuate the answer.
