`useRef` é um React Hook que permite **referenciar um valor que não é necessário para renderização**.
## Uso
### Referenciar um valor 
Chame `useRef` no nível mais alto do seu componente para declarar uma ou mais referências.
```jsx
import { useRef } from 'react';  

function Stopwatch() {  
	const intervalRef = useRef(0); // { current: 0 }
	// ...
```

`useRef` retorna um objeto ref com uma **única propriedade `current`** inicialmente definida com o valor inicial que você forneceu.

Nas próximas renderizações, **`useRef` retornará o mesmo objeto**. Você pode alterar sua propriedade `current` para **armazenar informações e lê-las mais tarde**. 

==**Alterar uma `ref` não desencadeia uma nova renderização.**== Isso significa que as referências são perfeitas para armazenar informações que não afetam a saída visual do seu componente.
#### Atenção
==**Não escreva ou leia `ref.current` durante a renderização.**==

Ler ou escrever uma `ref` **durante a renderização** interrompe o comportamento esperado.
```jsx
function MyComponent() {  
	// ...  
	// 🚩 Don't write a ref during rendering  
	myRef.current = 123;  
	// ...  
	// 🚩 Don't read a ref during rendering  
	return <h1>{myOtherRef.current}</h1>;  
}
```

Em vez disso, você pode ler ou escrever `refs` em manipuladores de eventos ou efeitos.
```jsx
function MyComponent() {  
	// ...  
	useEffect(() => {  
		// ✅ You can read or write refs in effects  
		myRef.current = 123;  
	});  
	// ...  
	function handleClick() {  
		// ✅ You can read or write refs in event handlers  
		doSomething(myOtherRef.current);  
	}  
	// ...  
}
```

Se você **precisar ler ou escrever** algo durante a **renderização**, use o `state`.

### Manipular o DOM
É particularmente comum usar um `ref` para manipular o DOM. O React possui suporte integrado para isso.

Primeiro, declare um **objeto `ref`** com um valor inicial `null`:
```jsx
import { useRef } from 'react';  

function MyComponent() {  
	const inputRef = useRef(null);  
// ...
```

Em seguida, **passe seu objeto ref** como o atributo `ref` para o JSX do DOM node que você deseja manipular:
```jsx
// ...  
return <input ref={inputRef} />;
```

O React definirá a propriedade atual do seu objeto ref para esse DOM node. Agora você **pode acessar o DOM node do `<input>`** e chamar métodos como `focus()`:
```jsx
function handleClick() {  
	inputRef.current.focus();  
}
```

O React definirá a propriedade atual como `null` quando o nó for removido da tela.
### Rastrear mudanças de estado
O Hook `useRef` também pode ser usado para **rastrear valores de estado anteriores**.
Isso ocorre porque podemos persistir valores `useRef` entre renderizações.

Exemplo:
```jsx
import { useState, useEffect, useRef } from "react";

function App() {
	const [inputValue, setInputValue] = useState("");
	const previousInputValue = useRef("");
	
	useEffect(() => {
		previousInputValue.current = inputValue;
	}, [inputValue]);
	
	return (
		<>
			<input
				type="text"
				value={inputValue}
				onChange={(e) => setInputValue(e.target.value)}
			/>
			<h2>Current Value: {inputValue}</h2>
			<h2>Previous Value: {previousInputValue.current}</h2>
		</>
	);
}
```
## Quando usar
Normalmente, você usará uma referência **quando seu componente precisar “sair” do React** e se **comunicar com APIs externas** – geralmente uma API de navegador que não afetará a aparência do componente. Aqui estão algumas dessas situações raras:
- Armazenar timeout IDs
- Armazenar e manipular elementos do DOM
- Armazenar outros objetos que não são necessários para calcular o JSX

==**Se o seu componente precisa armazenar algum valor, mas isso não afeta a lógica de renderização, escolha refs.**==