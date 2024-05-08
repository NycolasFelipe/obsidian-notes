Webpack takes all of our assets and outputs them to a production-ready bundle.
- Bundles JavaScript files into one file, minimizing http requests
- Process SASS / LESS files into CSS and only use them where needed
- Convert JSX or ES2015 into vanilla JS which browsers understand
- 
### Links:
- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/en)

### Installing Webpack & Bundling JS
```
npm init
npm i webpack --save-dev
npm i webpack-cli --save-dev
```
#### Obs.:
- `"dependencies"`: Packages required by your application in production.
- `"devDependencies"`: Packages that are only needed for local development and testing

### Webpack Config
[[Webpack Config]]

### TypeScript + Webpack
[[TypeScript + Webpack]]

### Combining JS Files
```
webpack script.js ./bundle.js
```

O que o webpack nos permite é combinar diversos arquivos diferentes em um único arquivo (script.js), formado por diversos módulos, em somente um módulo.

Dessa forma, é necessário realizar somente uma requisição HTTP, tornando a aplicação mais leve e otimizada.

### Exemplo:
#### script-1.js
```ts
let message = require("./script-2");
alert(message);
```
#### script-2.js
```js
module.exports = "tempus fugits";
```
#### bunde.js
```js
let message = "tempus fugits";
alert(message);
```

