## Exemplo de uso básico
```js
const items = [
	{ name: "Rice", price: 5 },
	{ name: "Book", price: 20 },
	{ name: "Chicken", price: 10 },
	{ name: "Monitor", price: 100 },
];

const totalPrice = items.reduce((total, item) => {
	return total + item.price;
}, 0);
```

Na função reduce, `total` é o **valor final que será retornado**, `item` é o **valor a ser trabalhado em cada iteração**, e o segundo parâmetro da função, `0`, é o **valor inicial para o total**.

Nesse caso, a **função reduce realiza a mesma tarefa que um loop `forEach`** faria para calcular a soma de todos os itens. **Porém o reduce permite guardar a soma em uma variável `const`**, além de ter uma leitura de **código mais limpa**.
## Exemplo de uso mais avançado
```js
const people = [
	{ name: "Kyle", age: 26 },
	{ name: "John", age: 31 },
	{ name: "Sally", age: 42 },
	{ name: "Will", age: 42 },
];

const result = people.reduce((groupedPeople, person) => {
	const age = people.age;
	if (groupedPeople[age] === null) {
		groupedPeople[age] = [];
	}
	groupedPeople[age].push(person);
	return groupedPeople;
}, {});
```

Nesse código, utilizamos o reduce para agrupar todas as pessoas em um único objeto, e as dividimos de acordo com a sua idade. Este seria o valor final da constante `result`:
```js
{
	26: [{ name: "Kyle", age: 26 }],
	31: [{ name: "John", age: 31 }],
	42: [{ name: "Sally", age: 42 }, { name: "Will", age: 42 }]
}
```

Seria possível realizar essa mesma tarefa através de um loop `forEach`, mas dessa forma **o código é muito mais legível** e a atribuição do resultado à uma **variável constante** torna a **aplicação menos suscetível à erros.**
## Exemplo de uso: encontrar o maior valor
```js
const items = [
	{ name: "Rice", price: 5 },
	{ name: "Book", price: 20 },
	{ name: "Chicken", price: 10 },
	{ name: "Monitor", price: 100 },
];

const result = items.reduce((prev, item) => {
	if (item.price > prev) {
		return item.price;
	}
	return prev;
}, 0);
```

Nesse código, o reduce foi utilizado para encontrar o **maior valor em uma dada propriedade de um objeto**, em uma **lista de objetos**.
## Exemplo de uso: encontrar o número de ocorrências
```js
const colors = ["green", "green", "red", "blue", "red", "red"];

const result = colors.reduce((prev, color) => {
	prev[color] = (prev[color] || 0) + 1;
	return prev;
}, {});
```

Nesse código, utilizamos o reduce para **contar o número de ocorrências** de uma string em um array. Este seria o valor final da constante `result`:
```js
{
	green: 2,
	red: 3,
	blue: 1
}
```