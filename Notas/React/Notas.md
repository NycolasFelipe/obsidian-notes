# Iniciando um projeto básico no React
## Comece com um protótipo inicial
```cmd
npx create-react-app project
```
## Acesse a pasta do projeto
```cmd
cd ./project
```
## Exclua os arquivos desnecessários
![[Pasted image 20240507202005.png]]
## Inicialize o projeto
```cmd
npm start
```

Dentro de `App.js` utilizar o atalho `rafce` _React Arrow Function Export Component_ para iniciar a edição do arquivo.

![[Pasted image 20240507132941.png]]

---
# Criando rotas
[Guia para criar rotas](https://v5.reactrouter.com/web/guides/quick-start)
## Instale o pacote de rotas do react
```cmd
 npm install react-router-dom
```
## Inicie uma rota básica dentro do arquivo `index.js`
![[Pasted image 20240507203302.png]]
## Utilizando links
Use o componente do react `Link` para redirecionar o usuário:
```jsx
  <Link to="/">Home</Link>
```
## Criando um gerenciador de rotas
`Routing.jsx`
```jsx
import React from "react";
import { Routes, Route, BrowserRouter as Router } from "react-router-dom";
//import Home, About, Topics... etc

const Routing = () => {
	return (
		<Router>
			<Switch>
				<Route path="/"><Home /></Route>
				<Route path="/about"><About /></Route>
		        <Route path="/topics"><Topics /></Route>
			</Switch>
		</Router>
	);
}

export default Routing;
```
---
# Utilizando ícones react
[React Icons](https://react-icons.github.io/react-icons/)
## Installation (for standard modern project)
```cmd
npm install react-icons --save
```
## Usage
```jsx
import { FaBeer } from 'react-icons/fa';

const App = () => {
	return <h3> Lets go for a <FaBeer />?</h3>
}
```

---
# Autenticação com Auth0
[Link para o site oficial](https://auth0.com/)
## Crie uma nova instância para a aplicação
![[Pasted image 20240507205900.png]]
 Em seguida, siga os passos descritos na aba `quickstart`

---
# Outras notas
## Reset Stylesheet
```css
* { 
	margin: 0;
	padding: 0; 
	font-family: sans-serif; 
	box-sizing: border-box; 
}
```

Explicação linha a linha:
 - This removes any default margin that browsers might apply to elements. Setting it to 0 ensures a consistent starting point for element spacing.
 
 - This removes any default padding that browsers might apply to elements. Setting it to 0 ensures a consistent starting point for element content placement.
 
 - This sets the default font family for all elements to a sans-serif font. This provides a clean and modern look for the page's text.
 
 - This changes the default way browsers calculate the width and height of elements. By default, browsers add the element's padding and border to its width and height when applying styles. Setting `box-sizing: border-box;` makes the element's width and height include its padding and border, ensuring more predictable layout behavior.
 