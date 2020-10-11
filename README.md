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

<<<<<<< HEAD
console.log(result)

// => { api_key:"123" }
=======
console.log(result);
>>>>>>> 024c49976a41ead1a83ad4e48ea85b33553177b5
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