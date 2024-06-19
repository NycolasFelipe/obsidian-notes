`useMemo` é um hook que **permite armazenar em cache o resultado de um cálculo entre renderizações**.
```jsx
const cachedValue = useMemo(calculateValue, dependencies)
```
## Referência
`useMemo(calculateValue, dependencies)`
Essa função deve ser chamada na **parte superior do componente**.
### Exemplo
```jsx
import { useMemo } from 'react';

function TodoList({ todos, tab }) {  
	const visibleTodos = useMemo(  
		() => filterTodos(todos, tab),  
		[todos, tab]  
		);  
	// ...  
}
```

## Parâmetros
- `calculateValue`: A função que calcula o valor que queremos armazenar em cache. Deve ser uma **função pura\***, não deve ter argumentos, e retornar um valor.
- `dependencies`: Lista de **valores reativos referenciados dentro da função**.
## Retorno
Na renderização inicial, `useMemo` **retornará o resultado da chamada da função `calculateValue`** sem argumentos.

Nas renderizações subsequentes, **será retornado ou o último valor armazenado da última renderização** (se as dependências permanecerem iguais), **ou será calculado e retornado um novo valor.**

## Exemplo de uso
### Evitar repetição de cálculos custosos
Para armazenar em memória cache o resultado de um cálculo, **basta envolvermos a função de cálculo com o `useMemo`** na parte superior do nosso componente:
```jsx
import { useMemo } from 'react';  
	function TodoList({ todos, tab, theme }) {  
	const visibleTodos = useMemo(
		() => filterTodos(todos, tab), 
		[todos, tab]
	);  
	// ...  
}
```
> Esse tipo de caching é chamado **memoization**.

<br/>

## Como dizer se um cálculo é custoso?
Em geral, exceto em casos em que fazemos um loop por milhares de objetos, provalmente não é custoso. Caso queiramos ter certeza, podemos adicionar um `console log` para medir o tempo gasto em um bloco de código:
```jsx
console.time('filter array');  
const visibleTodos = filterTodos(todos, tab);  
console.timeEnd('filter array');
```

Se o tempo de log for uma quantia significativa (por exemplo, acima de `1ms`), é recomendado utilizar **memoization**.

>Também é uma boa ideia **testar a performance em ambientes com performance artificialmente limitada.** Por exemplo, utilizando a ferramenta [CPU Throttling](https://developer.chrome.com/blog/new-in-devtools-61/#throttling) do Google Chrome.
