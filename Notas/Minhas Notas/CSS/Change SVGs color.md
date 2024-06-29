```html
<img src="dotted-arrow.svg" class="filter-green"/>
```
>Para mudar a cor essa imagem svg, podemos utilizar [essa ferramenta](https://codepen.io/sosuke/pen/Pjoqqp), ou [essa](https://isotropic.co/tool/hex-color-to-css-filter/) para converter cor hexadecimal em um filtro CSS.

Por exemplo:
```css
/* Converte a cor da imagem para verde */
filter: invert(48%) sepia(79%) saturate(2476%) hue-rotate(86deg) 
	brightness(118%) contrast(119%);
```
