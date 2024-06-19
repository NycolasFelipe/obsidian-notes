`useCallback` é um hook que **permite guardar a definição de uma função em memória cache** entre renderizações.
```jsx
const cachedFn = useCallback(fn, dependencies);
```
## Referência
`useCallback(fn, dependencies)`
Essa função deve ser chamada na **parte superior do componente**.
#### Exemplo
```jsx
import { useCallback } from 'react';  

function ProductPage({ productId, referrer, theme }) {  
	const handleSubmit = useCallback((orderDetails) => {  
		post('/product/' + productId + '/buy', {  
			referrer,  
			orderDetails
		});  
}, [productId, referrer]);  

// ...
```

## Parâmetros
- `fn`: A função que será armazenada em memória cache. 
- `dependencies`: Lista de **valores reativos referenciados dentro da função**.
## Retorno
No primeiro render, `useCallback` vai retornar a função `fn` fornecida.

Nos renders subsequentes, **será retornada a função `fn` armazenada em cache da última renderização**, mas somente se **nenhum valor da lista de `dependencies` tiver mudado**.
## Exemplo de uso 
### Pular renderização de componentes
Quando trabalhamos com otimização de performance, às vezes iremos precisar **armazenar em cache funções que passamos para componentes**.
#### Exemplo
Suponhamos que estamos passando uma função `handleSubmit` do componente pai `ProductPage` para o componente filho `ShippingForm`:
```jsx
function ProductPage({ productId, referrer, theme }) {  
// ...  
	return (  
		<div className={theme}>  
			<ShippingForm onSubmit={handleSubmit} />  
		</div>  
	);
```
Mudar o valor da propriedade `theme` faz com que todos os componentes filhos sejam renderizados novamente. De fato, em React, ==**quando um componente re-renderiza, todos seus filhos são re-renderizados recursivamente**==.

Esse comportamento **é aceitável para componentes que não precisam de muito cálculo** para serem renderizados. Mas caso a aplicação comece a tornar-se lenta, podemos **especificar que um componente só deve ser re-renderizado quando os valores de seus props mudarem**, através do uso do **`memo`**.

Exemplo:
```jsx
import { memo } from 'react';  
	const ShippingForm = memo(function ShippingForm({ onSubmit }) {  
	// ...  
	});
```
> **Para prevenir a re-renderização desnecessária de um componente**, podemos envolvê-lo com a keyword `memo`. Dessa forma, a re-renderização somente acontecerá caso ocorra uma mudança nas props do componente.

==**Em JavaScript, uma função `function () {}` ou `() => {}` sempre cria uma *função diferente***, assim como um objeto `{}` sempre cria uma nova referência==. 

Normalmente, isso não é um problema tão grande. Mas no exemplo anterior, como `onSubmit` muda a cada renderização, a otimização com o `memo` não está funcionando corretamente. Neste caso, podemos utilizar o hook `useCallback` para lidar com a situação:
```jsx
function ProductPage({ productId, referrer, theme }) {  
// Tell React to cache your function between re-renders...  
	const handleSubmit = useCallback((orderDetails) => {  
	post('/product/' + productId + '/buy', {  
		referrer,  
		orderDetails,  
	});  
}, [productId, referrer]); 
// ...so as long as these dependencies don't change...  

return (  
	<div className={theme}>  
		{/* ...ShippingForm will receive the same props*/}
		{/* and can skip re-rendering */}
		<ShippingForm onSubmit={handleSubmit} />  
	</div>  
	);  
}
```

## Quando useCallback deve ser usado?
Armazenar uma função em cache só é valida em alguns cenários:
- **Quando a função é passada para algum componente envolto em `memo`**. Memoization faz com que o componente seja re-renderizado somente quando as dependências mudarem.
- **A função criada será usada mais tarde como dependência de algum Hook**. Por exemplo, alguma outra função que usa `useCallback` depende desta função, ou esta função é utilizada dentro do **`useEffect`**.
