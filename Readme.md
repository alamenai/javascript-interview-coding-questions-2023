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
