Existem muitas formas de estilizar React utilizando CSS, sendo as principais:
- Inline styling
- CSS stylesheets
- CSS modules
## Inline Styling
To style an element with the inline style attribute, the value must be a **JavaScript object**:

Exemplo:
```jsx
const Header = () => {
	return (
		<>
			<h1 style={{color: "red"}}>Hello Style!</h1>
			<p>Add a little style!</p>
		</>
	);
}
```

>**Nota:** Em JSX, as expressões JavaScript são escritas entre chaves e, como os objetos JavaScript também usam chaves, o estilo no exemplo acima é **escrito entre dois conjuntos de chaves {{}}**.

<br />

### Nomes de propriedades camelCased
Como o CSS é escrito em um objeto JavaScript, as propriedades com separadores de hífen, como background-color, **devem ser escritas com a sintaxe camel case**:

Exemplo:
```jsx
const Header = () => {
	return (
		<>
			<h1 style={{backgroundColor: "lightblue"}}>Hello Style!</h1>
			<p>Add a little style!</p>
		</>
	);
}
```
### JavaScript Object
Você também pode **criar um objeto com informações de estilo** e fazer referência:

Exemplo:
```jsx
const Header = () => {
	const myStyle = {
		color: "white",
		backgroundColor: "DodgerBlue",
		padding: "10px",
		fontFamily: "Sans-Serif"
	};
	return (
		<>
			<h1 style={myStyle}>Hello Style!</h1>
			<p>Add a little style!</p>
		</>
	);
}
```
## CSS Stylesheet
Você pode escrever seu **estilo CSS em um arquivo separado**, salvar o arquivo com a extensão `.css` e **importá-lo em seu aplicativo**.
## CSS Modules
Módulos CSS são convenientes para componentes **colocados em arquivos separados**.

==O CSS dentro de um módulo está **disponível apenas para o componente que o importou** e você não precisa se preocupar com conflitos de nome.==

Crie o módulo CSS com a extensão `.module.css`, exemplo: `my-style.module.css`.
Importe a folha de estilo no seu componente:
```jsx
import styles from './my-style.module.css'; 

const Car = () => {
	return <h1 className={styles.bigblue}>Hello Car!</h1>;
}

export default Car;
```

