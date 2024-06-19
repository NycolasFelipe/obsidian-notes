O Hook `useReducer` é semelhante ao `useState`. Ele permite **lógica de estado personalizada**.

Se parte de uma aplicação **depender de múltiplos `state`** para atender uma lógico complexa, `useReducer` pode ser útil.
## Sintaxe
O `useReducer` aceita dois argumentos: 
```jsx
useReducer(reducer, initialState)
```

A função `reducer` contém sua lógica de estado personalizada e o `initialState` pode ser um valor simples, mas geralmente conterá um objeto.

O `useReducer` retorna **o `state` atual e um método `dispatch`**.
### Exemplo
```jsx
import { useReducer } from "react";

const initialTodos = [
	{
		id: 1,
		title: "Todo 1",
		complete: false,
	},
	{
		id: 2,
		title: "Todo 2",
		complete: false,
	},
];

const reducer = (state, action) => {
	switch (action.type) {
		case "COMPLETE":
			return state.map((todo) => {
				if (todo.id === action.id) {
					return { ...todo, complete: !todo.complete };
				} else {
				return todo;
			}
		});
		default:
			return state;
	}
};

function Todos() {
	const [todos, dispatch] = useReducer(reducer, initialTodos);
	
	const handleComplete = (todo) => {
		dispatch({ type: "COMPLETE", id: todo.id });
	};

	return (
		<>
			{todos.map((todo) => (
				<div key={todo.id}>
					<label>
						<input
							type="checkbox"
							checked={todo.complete}
							onChange={() => handleComplete(todo)}
						/>
						{todo.title}
					</label>
				</div>
			))}
		</>
	);
}
```
