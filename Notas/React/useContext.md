React Context é uma forma de **gerenciar o estado globalmente**.
Pode ser usado junto com o Hook `useState` para **compartilhar o estado entre componentes profundamente aninhados** com mais facilidade.
## O Problema
O estado deve ser mantido pelo componente pai mais alto na pilha que requer acesso ao estado. Para ilustrar, suponhamos que temos muitos componentes aninhadose que os componentes **na parte superior e inferior da pilha precisam de acesso ao estado**.

Para fazer isso sem Contexto, precisaremos **passar o estado como `props` através de cada componente** aninhado. Isso é chamado de **"prop drilling"**.

Exemplo:
```jsx
import { useState } from "react";

function Component1() {
	const [user, setUser] = useState("Jesse Hall");
	return (
		<>
			<h1>{`Hello ${user}!`}</h1>
			<Component2 user={user} />
		</>
	);
}

function Component2({ user }) {
	// Componente intermediário não usa a propriedade
	return (
		<>
			<h1>Component 2</h1>
			<Component3 user={user} />
		</>
	);
}

function Component3({ user }) {...}

function Component4({ user }) {...}

function Component5({ user }) {
	// Somente o último componente usa a propriedade
	return (
		<>
			<h1>Component 5</h1>
			<h2>{`Hello ${user} again!`}</h2>
		</>
	);
}
```
## A Solução
A solução é criar contexto.
Para criar contexto, você deve importar `createContext` e inicializá-lo:
```jsx
import { useState, createContext } from "react";
const UserContext = createContext();
```

Em seguida, usaremos o **Context Provider** para agrupar **a árvore de componentes** que precisam do contexto de estado.
### Context Provider
Envolva os componentes filhos no **Context Provider** e forneça o valor do estado.
```jsx
function Component1() {
	const [user, setUser] = useState("Jesse Hall");
	return (
		<UserContext.Provider value={user}>
			<h1>{`Hello ${user}!`}</h1>
			<Component2 user={user} />
		</UserContext.Provider>
	);
}
```
Agora todos os componentes desta árvore terão acesso ao contexto do usuário.
#### Múltiplos valores
```jsx
function Component1() {
	const [user, setUser] = useState("Jesse Hall");
	return (
		<UserContext.Provider value={{ user, setUser }}>
			<h1>{`Hello ${user}!`}</h1>
			<Component2 user={user} />
		</UserContext.Provider>
	);
}
```
### Use the `useContext` Hook
Para usar o Context em um componente filho, precisamos acessá-lo usando o **Hook useContext.** Dessa forma, podemos acessar o contexto do usuário em todos os componentes:
```jsx
import { useState, createContext, useContext } from "react";

const UserContext = createContext();

function Component5() {
	const { user } = useContext(UserContext);
	// const { user, setUser } = useContext(UserContext);
	return (
		<>
			<h1>Component 5</h1>
			<h2>{`Hello ${user} again!`}</h2>
		</>
	);
}
```
