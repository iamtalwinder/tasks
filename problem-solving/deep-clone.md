### Task: Implement a Deep Clone Function in JavaScript

**Objective**: Write a function named `deepClone` that creates a complete copy of an object, including all nested objects, arrays, and standard JavaScript types (String, Number, Date, Boolean, etc.). The function should ensure that the cloned object is entirely independent of the original, with no shared references.

#### Key Points:
- The `deepClone` function must handle nested structures, ensuring that each level is appropriately cloned.
- The function should work correctly with arrays, objects, and other common types, creating new instances as needed.

#### Boilerplate Code:

```javascript
function deepClone(obj) {
  // Implement deep clone logic here
}

// Test cases
const originalObject = {
  num: 1,
  str: 'string',
  bool: true,
  arr: [1, 2, 3],
  obj: { child: 'child' },
  func: function() { return 'hello'; },
};

const clonedObject = deepClone(originalObject);

console.log(clonedObject); // Output should show a deeply cloned object
console.log(clonedObject === originalObject); // Should log false
console.log(clonedObject.obj === originalObject.obj); // Should log false
console.log(clonedObject.arr === originalObject.arr); // Should log false
console.log(clonedObject.func === originalObject.func); // Should log false
```

```js
// Test case 1: Deep clone an object containing primitive types
const obj1 = { a: 1, b: 'string', c: true };
const clone1 = deepClone(obj1);
console.log(JSON.stringify(clone1) === JSON.stringify(obj1));  
console.log(clone1 !== obj1); 

// Test case 2: Deep clone an object containing a nested object
const obj2 = { a: { b: { c: 1 } } };
const clone2 = deepClone(obj2);
console.log(JSON.stringify(clone2) === JSON.stringify(obj2));  
console.log(clone2 !== obj2);  

// Test case 3: Deep clone an object containing an array
const obj3 = { a: [1, 2, 3] };
const clone3 = deepClone(obj3);
console.log(JSON.stringify(clone3) === JSON.stringify(obj3));  
console.log(clone3 !== obj3);

// Test case 4: Circular dep
const circularObj = {
    a: 1,
    b: {
      c: 2
    }
  };
  circularObj.b.d = circularObj;  // Create a circular reference
  const circularClone = deepClone(circularObj);

```