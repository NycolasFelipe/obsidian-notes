O Hook `useState` nos permite **monitorar o estado** em um componente de função.
## Import `useState`
Na parte superior do seu componente, **importe o Hook useState**.
```jsx
import { useState } from "react";
```
## Initialize `useState`
Inicializamos nosso estado chamando `useState` em nosso componente de função.
`useState` aceita um **estado inicial** e retorna **dois valores**:
- O estado atual.
- Uma função que atualiza o estado.

Exemplo:
```jsx
import { useState } from "react";

export const FavoriteColor = () => {
	const [color, setColor] = useState("");
}
```
>O primeiro valor, `color`, é o nosso **estado atual**.
>O segundo valor, `setColor`, é a **função** usada para **atualizar nosso estado**.
>Por fim, definimos o **estado inicial** como uma **string vazia**: `useState("")`.

<br />

## Read State
Agora podemos incluir nosso estado em qualquer lugar do nosso componente.
```jsx
import { useState } from "react";

export const FavoriteColor = () => {
  const [color, setColor] = useState("red");
  return <h1>My favorite color is {color}</h1>
}
```
## Update State
Para atualizar nosso estado, **usamos nossa função de atualização de estado**.
```jsx
import { useState } from "react";

export const FavoriteColor = () => {
	const [color, setColor] = useState("red");
	return (
		<>
			<h1>My favorite color is {color}</h1>
			<button
				type="button"
				onClick={() => setColor("blue")}
			>Blue</button>
		</>
	)
}
```
## What Can State Hold
O Hook `useState` pode ser usado para rastrear **strings, números, booleanos, arrays, objetos** e qualquer combinação destes.
## Updating Objects and Arrays in State
Quando o **estado é atualizado**, **todo o estado é substituído**. Se chamarmos apenas `setCar({color: "blue"})`, isso removeria a marca, modelo e ano do nosso estado.

Podemos usar o **spread operator**, do JavaScript, para nos ajudar. Por exemplo:
```jsx
import { useState } from "react";

export const Car = () => {
	const [car, setCar] = useState({
		brand: "Ford",
		model: "Mustang",
		year: "1964",
		color: "red"
	});
	
	const updateColor = () => {
		setCar(previousState => {
			return { ...previousState, color: "blue" }
		});
	}
	
	return (
		<>
			<h1>My {car.brand}</h1>
			<p>
				It is a {car.color} {car.model} from {car.year}.
			</p>
			<button
				type="button"
				onClick={updateColor}
            >Blue</button>
		</>
	)
}
```
