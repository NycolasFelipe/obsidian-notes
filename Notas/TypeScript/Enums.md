Enums are one of the few features TypeScript has which is not a type-level extension of JavaScript.

Enums allow a developer to define a set of named constants. Using enums can make it easier to document intent, or create a set of distinct cases. TypeScript provides both numeric and string-based enums.

### Numeric enums
An enum can be defined using the `enum` keyword.

```ts
enum Direction {
	Up = 1,
	Down,
	Left,
	Right,
}
```

Above, we have a numeric enum where `Up` is initialized with `1`. All of the following members are auto-incremented from that point on. In other words, `Direction.Up` has the value `1`, `Down` has `2`, `Left` has `3`, and `Right` has `4`.

If we wanted, we could leave off the initializers entirely, so `Up` would have the value `0`, `Down` would have `1`, etc.

Using an enum is simple: just access any member as a property off of the enum itself, and declare types using the name of the enum:

```ts
enum UserResponse {
	No = 0,
	Yes = 1,
}

function respond(recipient: string, message: UserResponse): void {
	// ...
}

respond("Princess Caroline", UserResponse.Yes);
```

### String enums
String enums are a similar concept, but have some subtle [runtime differences](https://www.typescriptlang.org/docs/handbook/enums.html#enums-at-runtime) as documented below. In a string enum, each member has to be constant-initialized with a string literal, or with another string enum member.

```ts
enum Direction {
	Up = "UP",
	Down = "DOWN",
	Left = "LEFT",
	Right = "RIGHT"
}
```
