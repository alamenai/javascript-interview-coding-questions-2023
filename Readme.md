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
