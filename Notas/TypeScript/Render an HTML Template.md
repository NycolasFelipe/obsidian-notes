Renderizar dinamicamente um elemento HTML por referência:
#### ListTemplate.ts
```ts
export class ListTemplate {
	constructor(private container: HTMLULListElement) {}

	render(heading: string, text: string, pos: 'start' | 'end') {
		const li = document.createElement('li');
		
		const h4 = document.createElemente('h4');
		h4.innerText = heading;
		li.append(h4);
		
		const p = document.createElement('p');
		p.innerText = text;
		li.append(p);
		
		if (pos === 'start') {
			this.container.prepend(li);
		} else {
			this.container.append(li);
		}
	}
}
```

#### app.ts
```ts
const form = ...; //HTMLFormElement
const heading = ...; //string
const text = ...; //string

const ul = document.querySelector('ul')!;
const list = new ListTemplate(ul);

form.addEventListener("submit", (e: Event) => {
	e.preventDefault();
	list.render(heading, text);
});
```
