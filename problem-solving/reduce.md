### 2. **Create a Prototype for Reduce**

**Problem Statement**:
Create a prototype method `myReduce` for the Array object that mimics the behavior of the built-in `Array.prototype.reduce` method.

**Requirements**:
- The method should not use the built-in `Array.prototype.reduce` method.

**Example**:

```javascript
Array.prototype.myReduce = // Your implementation here


const array = [1, 2, 3, 4];
const sum = array.myReduce((acc, curr) => acc + curr, 0);
console.log(sum); // Expected output: 10
```

### Test Cases:

```javascript

// Test 1
const array1 = [1, 2, 3, 4];
const sum = array1.myReduce((acc, curr) => acc + curr, 0);
console.log(sum); // Expected output: 10

// Test 2
const sum = array1.myReduce((acc, curr) => acc + curr, 1);
console.log(sum); // Expected output: 11

// Test 3
const product = array1.myReduce((acc, curr) => acc * curr);
console.log(product); // Expected output: 24

// Test 4
const array3 = ['a', 'b', 'c'];
const concatenated = array3.myReduce((acc, curr) => acc + curr, '');
console.log(concatenated); // Expected output: 'abc'
```