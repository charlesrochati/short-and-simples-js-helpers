# short-and-simple-js-helpers
Some js helpers i found along the way that are not worthy turning into a dependency

# Objectfy node args object
<details>
  <summary>Click to expand!</summary>

```js
const input = ["/usr/local/bin/node", "src/server.ts", "api_key=123"];

const separator = '=';

function objectfyNodeArgs(input = []) {
  let object = {};

  input.forEach((item = '', index) => {
    if (item.includes(separator)) {
       const [key, value] = item.split(separator)
       object[key]=value;
    }
  });

  return object;
}

const result = objectfyNodeArgs(input)

console.log(result)
```

</details>
