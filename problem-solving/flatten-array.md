### 1. **Flatten a Nested Array**

**Problem Statement**:
Write a function `flattenArray` that takes an array of arbitrarily nested arrays of integers and returns a flat version of it. The function should remove all nesting, leaving a single array with all the integers in the original structure.

**Requirements**:
- Do not use the Array.prototype.flat() method or similar built-in methods.
- The function should handle varying levels of nesting (e.g., arrays within arrays within arrays).
- Aim for an efficient solution both in terms of runtime and space complexity.

**Example**:

```javascript
function flattenArray(nestedArray) {
  // Your implementation here
}

const nestedArray = [1, [2, 3], [[4], [5, 6, [7], 8]], 9];
console.log(flattenArray(nestedArray));
// Expected output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```