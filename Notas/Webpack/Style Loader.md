[`style-loader`](https://webpack.js.org/loaders/style-loader/) takes CSS you've imported in your JavaScript files, and injects them as style tags into the DOM. 
### Getting started
To begin, you'll need to install `style-loader`. It's recommended to combine `style-loader` with the [`css-loader`](https://webpack.js.org/loaders/css-loader/)

```console
npm i style-loader css-loader --save-dev
```

Then add the loader to your `webpack` config. For example:
#### style.css
```css
body {
  background: green;
}
```
#### component.js
```js
import "./style.css";
```
#### webpack.config.js
```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ["style-loader", "css-loader"],
      },
    ],
  },
};
```
