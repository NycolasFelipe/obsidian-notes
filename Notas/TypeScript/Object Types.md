To define an object type, we simply list its properties and their types.

For example, here’s a function that takes a point-like object:

```ts
// The parameter's type annotation is an object type
function printCoord(pt: { x: number; y: number }) {
	console.log("The coordinate's x value is " + pt.x);
	console.log("The coordinate's y value is " + pt.y);
} 
printCoord({ x: 3, y: 7 });   
```

The type part of each property is also optional. If you don’t specify a type, it will be assumed to be `any`.
#### Optional Properties
Object types can also specify that some or all of their properties are _optional_. To do this, add a `?` after the property name:

```ts
function printName(obj: { first: string; last?: string }) {
	// ...
}

// Both OK
printName({ first: "Bob" });
printName({ first: "Alice", last: "Alisson" });
```

In JavaScript, if you access a property that doesn’t exist, you’ll get the value `undefined` rather than a runtime error. Because of this, when you _read_ from an optional property, you’ll have to check for `undefined` before using it.

### Generic Object Types
[[Generic Object Types]]

### Tuple Types
[[Tuple Types]]