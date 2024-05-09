 ### The primitives: `string`, `number`, and `boolean`
- `string` represents string values like `"Hello, world"`
- `number` is for numbers like `42`. JavaScript does not have a special runtime value for integers, so there’s no equivalent to `int` or `float` - everything is simply `number`
- `boolean` is for the two values `true` and `false`

### Arrays
To specify the type of an array like `[1, 2, 3]`, you can use the syntax `number[]`; this syntax works for any type (e.g. `string[]` is an array of strings, and so on). You may also see this written as `Array<number>`, which means the same thing.

### any
TypeScript also has a special type, `any`, that you can use whenever you don’t want a particular value to cause typechecking errors.

The `any` type is useful when you don’t want to write out a long type just to convince TypeScript that a particular line of code is okay.

### noImplicitAny
When you don’t specify a type, and TypeScript can’t infer it from context, the compiler will typically default to `any`.

You usually want to avoid this, though, because `any` isn’t type-checked. Use the compiler flag [`noImplicitAny`](https://www.typescriptlang.org/tsconfig#noImplicitAny) to flag any implicit `any` as an error.

### Type Annotations on Variables
When you declare a variable using `const`, `var`, or `let`, you can optionally add a type annotation to explicitly specify the type of the variable:

```ts
let myName: string = "Alice";`
```

In most cases, though, this isn’t needed. Wherever possible, TypeScript tries to automatically _infer_ the types in your code. For example, the type of a variable is inferred based on the type of its initializer:

```ts
// No type annotation needed -- 'myName' inferred as type 'string'
let myName = "Alice";   
```

### Functions
[[Functions]]
### Object Types
[[Object Types]]
### Union Types
[[Union Types]]
### Type Aliases
[[Type Aliases]]
### Enums
[[Enums]]