### Inicializar um novo projeto de typescript:
```console
tsc --init
```
### Inicializar npm
```console
npm init
```
### Instalar o webpack
```console
npm i webpack webpack-cli ts-loader -D
```
### Instalar o typescript
```console
npm i typescript -D
```

### Estrutura de pastas
#### src
Todos os códigos de desenvolvimento (source code) ficarão dentro dessa pasta. Esta pasta conterá o index.ts
#### public
Todos os arquivos finais que serão processados pelo site estarão nessa pasta. Esta pasta conterá o index.html

### Configurar o webpack.config.js
```js
const path = require("path");
module.exports = {
	entry: "./src/index.ts",
	output: {
		filename: "bundle.js",
		path: path.resolve(__dirname, "public")
	},
	module: {
		rules: [
			{
				test: /\.ts$/,
				use: "ts-loader",
				include: [path.resolve(__dirname, "src")]
			}
		]
	}
}
```
#### Criar script dentro do package.json para rodar o webpack
```json
{
	"scripts": {
		"build": "webpack",
		"test": "echo \"Error: no test specified\" && exit 1"
	}
}
```

### Instalar o webpack dev server
```console
npm i webpack-dev-server -D
```
#### Criar script dentro do package.json para rodar o webpack dev server
```json
{
	"scripts": {
		"build": "webpack",
		"server": "webpack-dev-server",
		"test": "echo \"Error: no test specified\" && exit 1"
	},
}
```

### Adicionar configuração no webpack config para uso de módulos
```js
const path = require("path");

module.exports = {
	resolve: {
		extensions: [".ts", ".js"]
	}
}
```

### Instalando jQuery
#### Instalando pacote npm
```console
npm i --save-dev @types/jquery
```
#### Habilitar reconhecimento do jQuery
```
// ################## Import jQuery ##################
const $ = require('./libraries/jquery-3.7.1.min');
//@ts-ignore
window.jQuery = $;
//@ts-ignore
window.$ = $;
// ###################################################
```
