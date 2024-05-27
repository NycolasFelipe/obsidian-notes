# Reset stylesheet
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
# Change SVGs color
## 1. Add the SVG image using an <img> tag.
```html
<img src="dotted-arrow.svg" class="filter-green"/>
```
## 2. To filter to a specific color, use the following [Codepen](https://codepen.io/sosuke/pen/Pjoqqp) to convert a hexadecimal color code to a CSS filter:
For example, output for `#00EE00` is
```css
filter: invert(42%) sepia(93%) saturate(1352%) hue-rotate(87deg) brightness(119%) contrast(119%);
```

Generate a filter for any color [here](https://isotropic.co/tool/hex-color-to-css-filter/).

## 3. Add the CSS filter into this class
```css
.filter-green {
    filter: invert(48%) sepia(79%) saturate(2476%) hue-rotate(86deg) 
		brightness(118%) contrast(119%);
}
```

# Flex space-between last item
![[Pasted image 20240514172806.png]]

Correção:
```CSS
.parent {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
}

.parent::after {
  content: "";
  flex: auto;
}
```

# Adicionar 3 pontos no fim do texto
```css
line-height: 1.4em;
max-height: 3em;
display: -webkit-box;
-webkit-box-orient: vertical;
-webkit-line-clamp: 2;
overflow: hidden;
```
