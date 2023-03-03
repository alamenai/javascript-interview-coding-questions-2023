<h1 align=center>
Refresh your JavaScript knowledge
</h1>
<hr>

## Get Started

1. Write code to get array of names from given array:

```javascript
const users = [
	{ name: 'John', age: 25, country: 'United States' },
	{ name: 'Anis', age: 31, country: 'Algeria' },
	{ name: 'Jemmy', age: 50, country: 'France' },
	{ name: 'Packard', age: 70, country: 'Germany' },
];
```

<details>
<summary>
Solution
</summary>

```javascript
// Using map function
const names = users.map(({ name }) => name);
// Using forEach function
const names = [];
users.forEach(({ name }) => name);
// Using for-of loop
const names = [];
for (const { name } of users) {
	names.push(name);
}
// Using for-loop
const names = [];
for (let index = 0; index < users.length; index++) {
	names.push(users[index]);
}
```

</details>

2. Get an array of **online** users from the given array:

```javascript
const users = [
	{ username: 'Jhon', isOnline: true },
	{ username: 'Alex', isOnline: false },
	{ username: 'Kelly', isOnline: false },
	{ username: 'Joma', isOnline: true },
	{ username: 'Peter', isOnline: false },
];
```

<details>
<summary>
Solution
</summary>

```javascript
// Using map filter and map functions
const onlineUsers = users
	.filter(({ username, isOnline }) => {
		if (isOnline) return username;
	})
	.map(({ username }) => username);
// Using forEach function
const onlineUsers = [];
users.forEach(({ username, isOnline }) => {
	if (isOnline) onlineUsers.push(username);
});
// Using for-of loop
const onlineUsers = [];
for (const { username, isOnline } of users) {
	if (isOnline) onlineUsers.push(username);
}
// Using for-loop
const onlineUsers = [];
for (let index = 0; index < users.length; index++) {
	if (users[index].isOnline) onlineUsers.push(users[index].username);
}
```

</details>

3. Sort the given array by **age**:

```javascript
const students = [
	{ name: 'Jhon', age: 20 },
	{ name: 'Alex', age: 22 },
	{ name: 'Kelly', age: 21 },
	{ name: 'Joma', age: 23 },
	{ name: 'Peter', age: 24 },
];
```

<details>
<summary>
Solution
</summary>

```javascript
// Using map and sort functions
const sortedAges = students
	.map(({ age }) => age)
	.sort((prev, next) => prev - next);
```

[Submit your solution](https://github.com/MenaiAla/javascript-interview-coding-questions-2023/pulls)

</details>

4. What is the output? and why?

```javascript
let variable;
console.log(typeof variable);
```

<details>
<summary>
Solution
</summary>
<br>

Output: `undefined`.

Because we **defined** the variable without **assigning** it any value, and the default value is `undefined`.

</details>

5. What is the output? and why?

```javascript
let variable = null;
console.log(typeof variable);
```

<details>
<summary>
Solution
</summary>
<br>

Output: `object`.

JavaScript has **7 primitive types**. All primitive types , except `null` can be tested with `typeof` operator.
`typeof null` returns `object`. If we want to check for `null` we have to use `===null`.

| Type      | `typeof` return | Wrapper |
| --------- | --------------- | ------- |
| Null      | `object`        | N/A     |
| Undefined | `undefined`     | N/A     |
| Boolean   | `boolean`       | Boolean |
| Number    | `number`        | Number  |
| BigInt    | `bigint`        | BigInt  |
| String    | `string`        | String  |
| Symbol    | `symbol`        | Symbol  |

</details>

6. What is the output? and why?

```javascript
console.log(variable);
let variable = 1;
```

<details>
<summary>
Solution
</summary>
<br>

Output: `ReferenceError: Cannot access 'variable' before initialization`.

Javascript has a default behavior which is moving the declaration to the top of the current scope (script or function). We call this behavior **Hoisting**.

In JavaScript we can declare a variable after it has been used. Hoisting is ofter considered a feature of `var` declarations.

However, we can consider the following behaviors as Hoisting:

| Hoisting    | Behavior                                                                                                                                                  |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Value       | Being able to use a variable's value in its scope before the line it is declared                                                                          |
| Declaration | Being able to reference a variable in its scope before the line it is declared, without throwing a `ReferenceError`, but the value is always `undefined`. |

`let` allows you to declare variables that are limited to the scope of a `block` statement, or expression on which it is used, unlike the `var` keyword, which declares a variable globally, or locally to an entire function regardless of block scope. The other difference between `var` and `let` is that the latter can only be accessed after its declaration is reached.

For this reason, `let` declarations are commonly regarded as non-hoisted.

</details>

7. What is the output? and why?

```javascript
console.log(variable);
variable = 1;
```

<details>
<summary>
Solution
</summary>
<br>

Output: `ReferenceError: variable is not defined`.

Because we access a variable that **does not exist** in the scope. This exception occurs when there is a non-existent variable referenced somewhere.

In JavaScript we declare variables using the keywords:

1. `var`
2. `let`
3. `const`

</details>

8. Create a `counter` function which has `increment` and `getValue` functions.

<details>
<summary>
Solution
</summary>

```javascript
function counter() {
	let counter = 0;
	return {
		increment: function (value) {
			return counter + value;
		},
		getValue: function () {
			return counter;
		},
	};
}
```

</details>

9. Write a function `concatenate` which concatenates `firstName` and `lastName` (`concatenate(firstName)(lastName)`).

<details>
<summary>
Solution
</summary>

```javascript
const concatenate = (firstName) => (lastName) => firstName + ' ' + lastName;
```

</details>

10. Write a `curry` function.

> **Function Currying** is a concept of breaking a function with many arguments into many functions with single argument in such a way, that the output is same. In other words, its a technique of simplifying a multi-valued argument function into single-valued argument multi-functions.

<details>
<summary>
Solution
</summary>
<br>
The concept of currying function is named after the <a href="https://en.wikipedia.org/wiki/Haskell_Curry">Haskell Brooks Curry</a> who developed it.

> By definition, Currying is a process of transforming a function with higher arity to a function with lower arity. Curry functions are higher order functions which takes a function as input and returns a function that accepts arguments of the input function and either invokes that function returning its result (if at least arity number of arguments have been provided) or returns a function that accepts the remaining arguments and so on

`curry :: ((a,b)=>c) -> a -> b -> c`

```javascript
const curry = (fn) => {
	const arity = fn.length;
	return function f1(...args) {
		if (args.length >= arity) {
			return fn(...args);
		} else {
			return function f2(...moreArgs) {
				return f1(...args.concat(moreArgs));
			};
		}
	};
};
```

</details>

11. Write a function that gets an array and an element and returns an array with this element.

<details>
<summary>
Solution
</summary>

```javascript
// Using push method ( not recommended )
const pushElement = (arr, el) => {
	arr.push(el);
	return arr;
};
// Using spread operator
const pushElement = (arr, el) => [...arr, el];
console.log(pushElement([1, 2, 3], 4));
```

</details>

12. Write a function that merges two arrays and returns an array.

<details>
<summary>
Solution
</summary>

```javascript
// Using push method ( not recommended )
const mergeArrays = (arr1, arr2) => {
	arr1.push(...arr2);
	return arr1;
};
// Using spread operator
const mergeArrays = (arr1, arr2) => [...arr1, ...arr2];
console.log(mergeArrays([1, 2, 3], [4, 5, 6]));
```

</details>

13. Remove all duplicates from the given array:

```javascript
const array = [1, 2, 2, 2, 3, 3, 4, 5, 8, 1, 10, 4, 9, 6];
```

<details>
<summary>
Solution
</summary>

```javascript
// Using forEach and includes
const removeDuplicates = (arr) => {
	let noDuplicates = [];
	arr.forEach((el) => !noDuplicates.includes(el) && noDuplicates.push(el));
	return noDuplicates;
};
// Using Set
const removeDuplicates = (arr) => [...new Set(arr)];
```

[Submit your solution](https://github.com/MenaiAla/javascript-interview-coding-questions-2023/pulls)

</details>
