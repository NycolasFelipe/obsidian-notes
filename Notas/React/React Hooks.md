Hooks permitem que componentes de função tenham acesso ao estado e outros recursos do React. Devido a isso, os **componentes de classe geralmente não são mais necessários**.

==Embora os Hooks geralmente substituam componentes de classe, **não há planos para remover classes** do React.==
## O que é um Hook?
Os Hooks nos permitem **"conectar" recursos do React**, como **métodos de estado e ciclo de vida**.
```jsx
import React, { useState } from "react";

function FavoriteColor() {
	const [color, setColor] = useState("red");
	
	return (
		<>
			<h1>My favorite color is {color}!</h1>
			<button
				type="button"
				onClick={() => setColor("blue")}
			>
				Blue
			</button>
		</>
	);
}
```

- Você deve importar Hooks do react.
- Aqui estamos usando o Hook useState para **monitorar o estado do aplicativo**.
- **State geralmente se refere a dados** ou propriedades do aplicativo que **precisam ser rastreados.**

==**Note:** Hooks **will not work** in React **class components**.==
## Principais Hooks
- [[useState]] - allows us to track state in a function component
- [[useEffect]] -  allows us to perform side effects in our components
- [[useContext]] - allow us to to manage state globally
- [[useRef]] - allow us to persist values between renders
- [[useReducer]] - allows for custom state logic
- [[useCallback]] - permite guardar a definição de uma função em memória cache
- [[useMemo]] - permite armazenar em cache o resultado de um cálculo entre renderizações
- [[Custom Hooks]]
