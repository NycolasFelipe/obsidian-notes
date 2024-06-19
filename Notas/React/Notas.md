## Iniciando um projeto básico no React
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
## Criando rotas
[Guia para criar rotas](https://v5.reactrouter.com/web/guides/quick-start)
### Instale o pacote de rotas do react
```cmd
 npm install react-router-dom
```
### Inicie uma rota básica dentro do arquivo `index.js`
![[Pasted image 20240507203302.png]]
### Utilizando links
Use o componente do react `Link` para redirecionar o usuário:
```jsx
  <Link to="/">Home</Link>
```
### Criando um gerenciador de rotas
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
## React Icons
[React Icons](https://react-icons.github.io/react-icons/)
### Installation (for standard modern project)
```cmd
npm install react-icons --save
```
### Usage
```jsx
import { FaBeer } from 'react-icons/fa';

const App = () => {
	return <h3> Lets go for a <FaBeer />?</h3>
}
```

---
## Autenticação com Auth0
[Link para o site oficial](https://auth0.com/)
### Crie uma nova instância para a aplicação
![[Pasted image 20240507205900.png]]
 Em seguida, siga os passos descritos na aba `quickstart`
## Slick slider
Slick slider para react, [link](https://react-slick.neostack.com/docs/get-started)
## \[Snippet] Preenchimento de formulário
```jsx
const [user, setUser] = useState({ 
	name: "", email: "", subject: "", message: ""
});

let name, value;

const data = (e) => {
	name = e.target.name;
	value = e.target.value;
	setUser({ ...user, [name]: value });
}
```

```JSX
<form method="POST">
	<input
		type="text"
		name="name"
		id="name"
		value={user.name}
		placeholder="Digite seu nome completo"
		required
		autoComplete="off"
		onChange={(e) => data(e)}
	/>
	<input
		type="email"
		name="email"
		id="email"
		value={user.email}
		placeholder="Digite seu endereço de e-mail"
		required
		autoComplete="off"
		onChange={(e) => data(e)}
	/>
	<input
		type="text"
		name="subject"
		id="subject"
		value={user.subject}
		placeholder="Informe o assunto do e-mail"
		required
		autoComplete="off"
		onChange={(e) => data(e)}
	/>
	<textarea
		name="message"
		id="message"
		value={user.message}
		placeholder="Sua mensagem..."
		required
		autoComplete="off"
		onChange={(e) => data(e)}
	>
	</textarea>
</form>
```
