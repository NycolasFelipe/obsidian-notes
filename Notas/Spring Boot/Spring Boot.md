# Spring & Spring Boot
Spring e Spring Boot são **frameworks** em Java usados para **construir aplicações**. São ferramentas que ajudam a **estruturar** o código de uma forma **eficiente e escalável**.
# Spring
Spring é um **framework amplo** que fornece vários módulos para **construir diferentes tipos de aplicações**. Existem módulos como **Spring MVC** para aplicação web, **Spring Data** para acesso a dados, **Spring Security** para autenticação e autorização, entre outros.

Sua versatilidade implica em uma **aplicação que requer muita configuração manual** de diversos componentes, para se obter um app pronto para uso.
# Spring Boot
Spring Boot torna trabalhar com Spring mais simples. Ele vem com diversas **configurações prontas e dependências mais comumente usadas** em aplicações Spring. Isso torna o **processo inicial bem mais rápido e prático**.
# Spring's Inversion of Container (IoC)
Spring Boot nos permite **configurar como e quando dependências serão utilizadas em tempo de execução**. Por exemplo, o uso de um banco de dados diferente de um ambiente, de produção por exemplo, para outro. 

IoC é comumente também chamada de **dependency injection (DI)**. Apesar disso não ser correto em todos os casos, no contexto de Spring, é comum dizer que **dependências são "injetadas" na aplicação** em tempo de execução.

[Mais sobre Spring's IoC](https://docs.spring.io/spring-framework/reference/core/beans.html)

# Tópicos Importantes
## Spring Initializr
Ao começar uma nova aplicação Spring Boot, **o primeiro passo é utilizar o [[Spring Initializr]]**. Após algumas configurações iniciais, ele rapidamente irá **gerar uma aplicação Spring Boot pronta para uso**.
## API Contracts
A indústria de software adotou vários padrões para capturar o comportamento acordado da API na documentação e no código. Esses acordos são frequentemente **chamados de “contratos”**. Para desenvolvermos uma aplicação em Spring Boot, precisamos entender o conceito de [[API Contracts]].
## Testing First
É comum que as equipes de desenvolvimento de software criem conjuntos de testes automatizados para se protegerem contra regressões. Frequentemente, esses testes são escritos após a criação do código do recurso do aplicativo. Isso é chamado de desenvolvimento orientado a testes (TDD — **[[Test Driven Development]]**).