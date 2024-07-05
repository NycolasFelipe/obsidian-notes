## Sumário
The [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification is a lightweight convention on top of commit messages. **It provides an easy set of rules for creating an explicit commit history**; which makes it easier to write automated tools on top of. This convention dovetails with [SemVer](http://semver.org/), by describing the features, fixes, and breaking changes made in commit messages.

The commit message should be structured as follows:
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```
## Type: tipos de commit
O **type** é responsável por nos dizer qual o tipo de alteração ou iteração está sendo feita, das regras da convenção, temos os seguintes tipos:

`test`: indica qualquer tipo de criação ou alteração de códigos de teste. 
**Exemplo:** Criação de testes unitários.

`feat`: indica o desenvolvimento de uma nova feature ao projeto. 
 **Exemplo:** Acréscimo de um serviço, funcionalidade, *endpoint*, etc.

`refactor`: usado quando houver uma refatoração de código que não tenha qualquer tipo de impacto na lógica/regras de negócio do sistema. 
**Exemplo:** Mudanças de código após um *code review*.

`style`: empregado quando há mudanças de formatação e estilo do código que **não alteram** o sistema de nenhuma forma.  
  **Exemplo:** Mudar o _style-guide_, mudar de convenção _lint_, arrumar indentações, remover espaços em brancos, remover comentários, etc.

`fix`: utilizado quando há correção de erros que estão gerando bugs no sistema.  
  **Exemplo:** Aplicar tratativa para uma função que não está tendo o comportamento esperado e retornando erro.

`chore`: indica mudanças no projeto que não afetem o sistema ou arquivos de testes. São mudanças de desenvolvimento.  
  **Exemplo:** Mudar regras do _eslint_, adicionar _prettier_, adicionar mais extensões de arquivos ao ._gitignore_.
  
`docs`: usado quando há mudanças na documentação do projeto.  
**Exemplo:** adicionar informações na documentação da API, mudar o _README_, etc.

`build`: utilizada para indicar mudanças que afetam o processo de build do projeto ou dependências externas.  
**Exemplo:** _Gulp_, adicionar/remover dependências do _npm_, etc.

`perf`: indica uma alteração que melhorou a performance do sistema.  
**Exemplo:** alterar _ForEach_ por _while_, melhorar a query ao banco, etc.

`ci`: utilizada para mudanças nos arquivos de configuração de CI.  
**Exemplo:** _Circle_, _Travis_, _BrowserStack_, etc.

`revert`: indica a reverão de um _commit_ anterior.

### Observações
- Só pode ser utilizado um _type_ por _commit;_
- O _type_ é **obrigatório;**
- Caso esteja indeciso sobre qual _type_ usar, provavelmente trata-se de uma grande mudança e é possível separar esse _commit_ em dois ou mais _commits;_
- A diferença entre `build` e `chore` pode ser um tanto quanto sutil e pode gerar confusão, por isso devemos ficar atentos quanto ao tipo correto. No caso do Node.js por exemplo, podemos pensar que quando há uma adição/alteração de certa dependência de desenvolvimento presente em `devDependencies,` utilizamos o `chore.` Já para alterações/adições de dependências comuns aos projeto, e que haja impacto direto e real sobre o sistema, utilizamos o `build`.

## Scope: contextualizando o commit
Mesmo o _scope_ **não sendo obrigatório**, ele pode ser utilizado para contextualizar o _commit_ e trazer menos responsabilidade para a descrição, uma vez que dispondo do tipo de _commit_ e o contexto que foi aplicado, a mensagem deve ser o mais breve e concisa possível. **Lembrando que o _scope_ deve ser inserido no _commit_ entre parênteses**.

Além disso, no caso do _scope_ é possível adicionarmos múltiplos valores, como por exemplo: Caso houvesse uma refatoração de código em um repositório com versões mobile, web e desktop. A qual afeta o contexto mobile e web, poderíamos escrever o _commit_ da seguinte maneira:

```
git commit -m "refactor(web/mobile): changeCreateUser() logs"
```
>Dessa maneira indicamos que é um commit de refatoração que afetara os contextos mobile e web da aplicação.

<br>

### Observação
Os escopos devem ser separados com `/` , `\` ou `,`.
