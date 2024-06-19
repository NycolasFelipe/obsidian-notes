O Hook `useEffect` permite executar **efeitos colaterais** em componentes.
Alguns exemplos de efeitos são: **fetch de dados, atualização do DOM e temporizadores**.
`useEffect` aceita dois argumentos. O segundo argumento é opcional.

`useEffect(<função>, <dependência>)`
## Usos
Existem 3 principais formas de se utilizar esse hook:

**I. Nenhuma dependência:**
```jsx
useEffect(() => {
	//Runs on every render
});
```

**II. Array vazio:**
```jsx
useEffect(() => {
	//Runs only on the first render
}, []);
```

**III. Mudanças em props ou state:**
```jsx
useEffect(() => {
	//Runs on the first render
	//And any time any dependency value changes
}, [prop, state]);
```
## Effect Cleanup
**Timeouts, subscriptions, event listeners**, e outros efeitos que não são mais necessários devem ser descartados.
Fazemos isso incluindo uma **função de retorno no final do Hook** `useEffect`.
## Exemplo:
Limpar o cronômetro no final do Hook `useEffect`:
```jsx
import { useState, useEffect } from "react";

function Timer() {
	const [count, setCount] = useState(0);
	
	useEffect(() => {
		let timer = setTimeout(() => {
			setCount((count) => count + 1);
		}, 1000);
		
		return () => clearTimeout(timer);
	}, []);
	
	return <h1>I've rendered {count} times!</h1>;
}
```
