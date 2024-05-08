One final note about tuple types - tuple types have `readonly` variants, and can be specified by sticking a `readonly` modifier in front of them - just like with array shorthand syntax.

```ts
function doSomething(pair: readonly [string, number]) {
	// ...
}
```

As you might expect, writing to any property of a `readonly` tuple isn’t allowed in TypeScript.

Tuples tend to be created and left un-modified in most code, so annotating types as `readonly` tuples when possible is a good default.