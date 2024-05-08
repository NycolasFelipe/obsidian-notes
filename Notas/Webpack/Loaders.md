- Perform transformations
- E.g. Babel loaders transform ES2015 or JSX in vanilla JS
- Many more loaders for other things too (such as SASS)

### Using Babel Loaders
[Babel](https://babeljs.io/)
- Install babel-core and babe-loader via npm
- Install any presets we will be using to perform transformations via npm (e.g. with we want to transform ES2015 code, we need to set a specific preset)
- Configure webpack.config to tell webpack to use babel to transform our code

#### cmd
```
npm i babel-loader @babel/core --save-dev
npm i @babel/preset-env --save-dev ### enables transforms for ES2015+
```

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
	
	//module
	module: {  
		rules: [  
			{  
				test: /\.m?js$/,  
				exclude: /node_modules/,  
				use: {  
					loader: "babel-loader",  
					options: {  
						presets: ['@babel/preset-env']  
					}  
				}  
			}  
		]  
	}
}
```
