## O que é React?
- React é uma **biblioteca** de JavaScript **para construção de interfaces** p/ usuários, criado pelo Facebook.
- React é usado para construir ***Single Page Applications* (SPA)**.
- React nos permite criar **componentes reutilizáveis**.
## Configurar um ambiente React
Abra o terminal no diretório desejado para a aplicação e execute o seguinte comando:
```cmd
npx create-react-app _appname_
```
Navegue para o diretório da aplicação
```cmd
cd _appname_
```
Execute esse comando para iniciar a aplicação
```cmd
npm start
```
A aplicação começará a rodar no endereço `localhost:3000`.
## Como o React funciona?
==O React cria um **DOM VIRTUAL** na memória.==
>DOM significa **Document Object Model**. É utilizado por navegadores para representar a página web. Ele é responsável por fornecer uma **representação estruturada** do documento, como se fosse uma espécie de árvore com galhos, **definindo métodos para que possam ser alterados estrutura, estilo e conteúdo** do documento.

Em vez de manipular diretamente o DOM do navegador, o React cria um DOM virtual na memória, **onde faz todas as manipulações necessárias**, antes de fazer as alterações no DOM do navegador.

==React encontra as mudanças que foram feitas, e **só muda o que precisa ser mudado.**==
## Estilizando React usando CSS: [[React CSS]]
## React Hooks: [[React Hooks]]
## Notas: [Notas](Notas)
