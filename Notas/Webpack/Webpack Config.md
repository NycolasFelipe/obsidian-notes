O arquivo de configuração do webpack serve para que possamos gerar o arquivo `bundle.js` apenas executando o comando `webpack`.

Para isso, precisamos criar o arquivo `webpack.config.js`
#### webpack.config.js
```js
const path = require("path");

module.exports = {
	//mode
	mode: "production",
	
	//define entry point
	entry: path.resolve(__dirname, "./src/script.js"),
	
	//output point
	output: {
		path: path.resolve(__dirname, "./build"),
		filename: "bundle.js"
	}
}
```

#### package.json
```json
{
	"name": "webpack",
	"version": "1.0.0",
	"description": "",
	"main": "index.js",
	"scripts": {
		"test": "echo \"Error: no test specified\" && exit 1",
		"build": "webpack" //adicionar essa linha
	},
	"author": "",
	"license": "ISC",
	"devDependencies": {
		"webpack": "^5.91.0",
		"webpack-cli": "^5.1.4"
	}
}
```

#### cmd
```
npm run build
```

### Loaders
[[Loaders]]

### Style Loader
[[Style Loader]]
