# Find Closest Value In BST

- [Link to problem](https://www.algoexpert.io/questions/Find%20Closest%20Value%20In%20BST)

## Solution

```js
function findClosestValueInBst(tree, target) {
  return helper(tree, target, Infinity); // 1
}

function helper(tree, target, closest) {
  if (tree === null) return closest; // 2

  // 3
  if (Math.abs(target - closest) > Math.abs(target - tree.value)) {
    closest = tree.value;
  }

  // 4
  if (target > tree.value) {
    return helper(tree.right, target, closest);
  } else if (target < tree.value) {
    return helper(tree.left, target, closest);
  } else {
    return closest;
  }
}

// This is the class of the input tree. Do not edit.
class BST {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}
```

### Explanation

1. Define a helper function that will run recursivly. We need to pass it the entire tree, the target we are looking for, and our current closest value (which we can start at infinity)
2. First check, if we are at the end of our tree, then we can just return null
3. Next we calculate the absolute different between the target and our current closest value. And the target and our current tree value. If the tree value is closer than we can update our closest value to that.
4. Next we check to see which direction down the tree we head. If the target is larger we head right, if it is smaller than we head left. Otherwise we have found the number and we can return it!
