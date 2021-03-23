# Node Ecosystem, TDD, CI/CD

- `Array.map()`:

The `map()` method creates a **new array** with the results of calling a function for every array element, calls the provided function once for each element in an array, in order. does not execute the function for array elements without values and this method does not change the original array.

- `Array.reduce()` :

The `reduce()` method reduces the array to a **single value**, executes a provided function for each value of the array (from left-to-right) and return value of the function is stored in an accumulator (result/total).
Does not execute the function for array elements without values and This method does not change the original array.

- `superagent()`:

1. With normal Promise `.then()`:

```
superagent.post('/api/pet')
.then(console.log)
.catch(console.error);

```

2.  with `async` / `await`:

```
(async () => {
  try {
    const res = await superagent.post('/api/pet');
    console.log(res);
  } catch (err) {
    console.error(err);
  }
})();

```

- promises:

A JavaScript Promise object can be:

1. Pending
2. Fulfilled
3. Rejected

The Promise object supports two properties: state and result While a Promise object is "pending" (working), the result is undefined.
When a Promise object is "fulfilled", the result is a value When a Promise object is "rejected", the result is an error object.

- Are all callback functions considered to be Asynchronous?

Simply taking a callback doesn't make a function asynchronous. There are many examples of functions that take a function argument but are not asynchronous. For example there's forEach in Array. It iterates over each item and calls the function once per item.

This can be used among other things to calculate total value from a property of each item.
example:

```
let totalSize = 0;
items.forEach((item) => {
totalSize += item.size;
});
return totalSize;

```
