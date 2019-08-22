# Callback functions that are built into `Array`
- Array.filter()
- Array.reduce()
- Array.map()


## Array.filter()
#### [Link to video](https://www.youtube.com/watch?v=BMUiFMZr7vk&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84&index=1)
`Array.filter()` takes a single argument, a function, and expects it to return either `true` or `false`

It will run your function for every value in the array,and return another array that with ever value that returned `true` in your function.

For example, if you had an array of numbers:
```js
const arrayOfNumbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
```
and you wanted to get _just_ the even numbers, you could use `filter` like this:
```js
const evenNumbers = arrayOfNumbers.filer(function(num) {
  return num / 2 === 0;
});
```
This will run your function with every value in `arrayOfNumbers` and put that value in `evenNumbers` if your function returns true.


You can use an arrow function to make this smaller, as well.
```js
const evenNumbers = arrayOfNumbers.filter(num => num % 2 === 0);
```
_note: You don't need curly brackes around the function or a return statment if the function is just one statment_

_note: Theres another funtion called `Array.reject()` that works the same way, except the other way around_

## Array.reduce()
#### [Link to video](https://www.youtube.com/watch?v=Wl98eZpkp-c&index=3&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)
`Array.reduce()` will take two arguments; a callback function, and an second value, that will be passed into the callback function.

```js
const arrayOfNumbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

let total = arrayOfNumbers.reduce(function(totalValue, currentNum){/*...*/}, 0);
```
The first value passed through is a function, and the second value, `0`, is going to be passed through to the CB function as the first parameter, which is `totalValue` in this case.
The second argument in the Callback function, `currentNum`, is the iterated value from the original array

For example, the following gets the total value of `arrayOfNumbers`

```js
let total = arrayOfNumbers.reduce(function(totalValue, currentNum){
  return totalValue += currentNum;
}, 0);
```

And again, we can use an _arrow function_ to make this a bit cleaner

```js
let total = arrayOfNumbers.reduce((totalValue, currentNum) => totalValue += currentNum, 0);
```

## Array.map()
#### [Link to video](https://www.youtube.com/watch?v=bCqtb-Z5YGQ&index=2&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)
`Array.map()` will take a single argumemt, which will be your callback function. It expects your CB function to return a transformed (or the same) value, which will be put into a new array

Using the same array from before: 
```js
const arrayOfNumbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
```

we'll use `map` to multiple ever even number by 2, and leave the odd numbers the same

```js
let newArr = arrayOfNumbers.map(function(num){
  if (num % 2 === 0) {
    return num * 2;
  } else {
    return num;
  }
})
```
This is iterating through `arrayOfNumbers`, passing it to your callback function, and creating a new array, `newArr`, the all the values returned from the CB function.


and of course we can minify this more using arrow functions and refactoring a bit
```js
let newArr = arrayOfNumbers.map(num => (num % 2 === 0) ? num * 2 : num);
```
