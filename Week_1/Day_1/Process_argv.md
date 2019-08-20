`process.argv` is a built-in array in Node that makes it easy to get arugments passed through the CLI.

The first element is the path to the `node` executable, and the second element is the name of the javascript file. All elements after that are the arugments passed from the CLI.

```
for (let i = 0; i < process.argv.length; i++) {
  console.log(`${i} ==> ${process.argv[i]}`);
}
```