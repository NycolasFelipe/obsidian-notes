Classes em TypeScript funcionam de forma semelhante à ja existente em JavaScript. 
Por exemplo, uma classe que descreve a fatura de um cliente:

```ts
class Invoice {
	client: string;
	details: string;
	amount: number;
	
	constructor(c: string, d: string, a: number) {
		this.client = c;
		this.details = d;
		this.amount = a;
	}

	format() {
		return `${this.client} owes ${this.amount} for ${this.details}`;
	}
}
```

Assim como podemos criar objetos para diferentes tipos (string, number, etc), podemos criar arrays que aceitam somente objetos de uma classe específica:

```ts
const invoices: Invoice[] = [];
const inv1 = new Invoice("mario", "work", 100);
const inv2 = new Invoice("luigi", "work", 200);
const inv3 = "500";
invoices.push(inv1); //OK
invoices.push(inv2); //OK
invoices.push(inv3); //Erro: variável do tipo string não pode ser atribuída
```

### Public, Private & Readonly
Para garantir o encapsulamento da classe, podemos declarar suas propriedades diretamente no construtor, utilizando as keywords de acesso para cada caso:

```ts
class Invoice {
	constructor(
		readonly client: string,
		private details: string,
		public amount: number
	) {};

	format() {
		return `${this.client} owes ${this.amount} for ${this.details}`;
	}
}
```
#### Member Visibility
 - `public` is the default visibility of class members. A `public` member can be accessed anywhere.
 - `protected` members are only visible to subclasses of the class they’re declared in.
 - `private` is like `protected`, but doesn’t allow access to the member even from subclasses:
#### Static Members
Classes may have `static` members. These members aren’t associated with a particular instance of the class. They can be accessed through the class constructor object itself:

```ts
class MyClass {
	static x = 0;
}

console.log(MyClass.x); //OK
```

Static members can also use the same `public`, `protected`, and `private` visibility modifiers:

```ts
class MyClass {
	private static x = 0;
}

console.log(MyClass.x); //Erro
```
