# Map

- Map is like an object, but the main difference is that it allows keys of any type.

- Methods, set, get, has, delete, clear, size

- Looping over a map: keys, values or entries.

- Map has a forEach method built-in.

- Init a map with an array of key value pairs: `new Map([['1',  'str1'], [1,    'num1'], [true, 'bool1']])`

- To turn an object into a Map, we can use `Object.entries`, which returns an array of key/value pairs: `const map = new Map(Object.entries(obj));`.

- Object.fromEntries, given an array of key/value paires, creates an object from it, we can use it to turn a Map into an object. `const obj = Object.fromEntries(map.entries()/map);`.


# Set

- Set of values, no keys, where each value may only exist once, unique.

- Create via `new Set()`.

- Methods: add, delete, has, clear, size

- Only works with values.


# WeakMap and Weakset

WeakSet can only contain objects, not primitive values. Like WeakMap, the "weakness" refers to the fact that the presence of an object in a WeakSet does not prevent the object from being garbage collected. If there are no other references to an object stored in a WeakSet, that object can be cleaned up by the garbage collector.

WeakMap can only have objects as keys. The reason for this limitation is tied to how garbage collection works in JavaScript. The "weakness" (i.e., the ability to be garbage collected) applies to the keys of the WeakMap. Primitive data types (like numbers or strings) are not collected in the same way as objects, so they can't be used as keys in a WeakMap.

## Caching Expensive Function Results

Using a `WeakMap` for caching results of expensive functions based on objects is beneficial. This technique is especially useful when:

- **The function is computationally intensive**: If the function takes considerable time or resources to compute a result based on an object, caching the result saves future computation time.
- **The input is object-based**: When the function relies on objects as input, using these objects as keys in a `WeakMap` allows for quick retrieval of cached results without modifying the objects themselves.
- **Memory efficiency is a concern**: `WeakMap` ensures that once the object is no longer needed (i.e., no other references exist), both the object and its associated cached result can be garbage collected, which helps in managing memory efficiently.
