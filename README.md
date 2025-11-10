# swe-sr-1-3

## Setup

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/how-tos/working-with-assignments#how-to-work-on-assignments).

Here are some useful commands to remember.

```sh
npm i                   # install dependencies
git checkout -b draft   # switch to the draft branch before starting

git add -A              # add a changed file to the staging area
git commit -m 'message' # create a commit with the changes
git push                # push the new commit to the remote repo
```

## Question 1

Read the documentation for `findIndex` and `indexOf` on MDN:

- [findIndex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
- [indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf).

Explain the difference between the methods and explain when you would choose one over the other. Provide examples to enhance your response.

### Response

According to MDN the `findIndex()` array method returns the index of the **first** element, but only returns the first index of the element when it satisfies the condition of a function. If no elements satisfy the condition, then -1 will be returned.

## Example of `findIndex()` syntax:

```js
const arr = [1, 6, 3, 4, 5, 4, 8, 7, 3];

const isEven = (element) => element % 2 === 0;

console.log(arr.findIndex(isEven));
// expected output: 1
```

### Breaking down syntax

In the example above I declare an array by the name of `arr`, in this array we have several different numbers randomized. Below the declaration of this array the variable `isEven` is also declared. In this variable it takes in the parameter `element` which is then used in the arrow function that checks if the element is divisible by 2 and has the remainder of 0. If the condition is true for any of the elements in the array, then it will return the index for that element that passes the condition.

## `indexOf()`

According to MDN, the `indexOf()` array method returns the **first** index of a given element in the array, but if the given element is not present in the array it will return -1. If there are other indexes in the array that hold that element, it will **not** return those indexes, because it will stop at the first index it finds that matches.

## Example of `indexOf()` syntax:

```js
const myGarage = [
  "Ferrari F80",
  "Pagani Huayra",
  "Koenigsegg Gemera",
  "Porsche 911 GT3",
  "Lamborghini SVJ",
  "Bugatti Chiron",
];

console.log(myGarage.indexOf("BMW M4"));
// expected output: -1
console.log(myGarage.indexOf("Porsche 911 GT3"));
// expected output: 3
```

## Breaking down the syntax

In the provided example above I declared an array called `myGarage`, in this array there’s a list of several hypercars. Below the array I am console logging 2 different elements for the `indexOf()` method to look for in the given array. We first pass the `myGarage` into the method by using **dot notation**. In the first console log I give it the string "BMW M4", this returns -1 because after the system searches the array there is no index with the given element hence the output of -1.

In the second console log I give it the string "Porsche 911 GT3", this element is actually in the array, so the system begins its search through the array and finds an index where it matches the given string to look for, therefore it returns its index of 3 because the element is in the **third** index.

## `indexOf()` vs. `findIndex()`

When comparing the `indexOf()` method and the `findIndex()` method, both are somewhat similar, but are different in terms of what instructions they are given and what exactly they return. For starters, unlike the `findIndex()` method where it uses a condition in order to search and return an index from an array, the `indexOf()` method returns the index just by giving it a string that matches an element within the array. Once it finds it, the output will be the index of that element.

If I were in a predicament where I would want to find a specific value in a very large array where it’s difficult to find it by reading, then I would use the `indexOf()` method.

If I were in a predicament where I would want to find a specific element in an array but **only** if it passes my test — for example, if it’s greater than 100 — then I would use the `findIndex()` method.
