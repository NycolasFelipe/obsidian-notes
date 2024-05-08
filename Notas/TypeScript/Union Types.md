TypeScript’s type system allows you to build new types out of existing ones using a large variety of operators.
#### Defining a Union Type
A union type is a type formed from two or more other types, representing values that may be _any one_ of those types. We refer to each of these types as the union’s _members_.

Let’s write a function that can operate on strings or numbers:

```ts
function printId(id: number | string) {
	console.log("Your ID is: " + id);
}

// OK
printId(101);

// OK
printId("202");

// Error
printId(false);
```

```ts
let mixed: (string|number)[] = [];
let anotherMixed: Array<(string|number)> = [];
```
