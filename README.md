# short-and-simple-js-helpers
Some js helpers i found along the way that are not worth turning into a dependency


---

<details>
  <summary>Objectfy node args object</summary>

```js
const input = ["/usr/local/bin/node", "src/server.ts", "api_key=123"];

const separator = '=';

function objectfyNodeArgs(input = []) {
  let object = {};

  input.forEach((item = '') => {
    if (item.includes(separator)) {
       const [key, value] = item.split(separator)
       object[key]=value;
    }
  });

  return object;
}

const result = objectfyNodeArgs(input);

console.log(result)

// => { api_key:"123" }
```
</details>


---

<details>
  <summary>Group by</summary>

```js
var groupBy = function(xs, key) {
  return xs.reduce(function(rv, x) {
    (rv[x[key]] = rv[x[key]] || []).push(x);
    return rv;
  }, {});
};

console.log(groupBy(['one', 'two', 'three'], 'length'));

// => {3: ["one", "two"], 5: ["three"]}
```

</details>

---

<details>
  <summary>Split array into chunks</summary>

```js
function chunk(array, chunkSize) {
  return [].concat.apply([],
    array.map(function(elem, i) {
      return i % chunkSize ? [] : [array.slice(i, i + chunkSize)];
    })
  );
}

console.log(chunk([1, 2, 3, 4, 5, 6, 7], 3))
// => (3) [[1, 2, 3], [ 4, 5, 6 ], [ 7 ] ]
```

</details>