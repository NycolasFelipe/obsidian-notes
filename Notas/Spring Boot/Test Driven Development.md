Por que aplicar TDD? O benefício do “test-drive” do código do aplicativo **é que os testes orientam você a escrever o código mínimo necessário** para satisfazer a implementação. Quando os testes são aprovados, você tem uma **implementação funcional** (o código do aplicativo) e uma **proteção contra a introdução de erros** no futuro.
# The Testing Pyramid
Diferentes testes podem ser escritos em diferentes níveis do sistema. Em cada nível, existe um equilíbrio entre a velocidade de execução, o “custo” para manter o teste e a confiança que ele traz para a correção do sistema. Esta hierarquia é frequentemente representada como uma “pirâmide de testes”.

![[Pasted image 20240519162738.png]]

**Testes de Unidade:** Um Teste de Unidade **exercita uma pequena “unidade” do sistema** que está isolada do resto do sistema. **Eles devem ser simples e rápidos.** Você deseja uma alta proporção de testes de unidade em sua pirâmide de testes, pois eles são essenciais para projetar software altamente coeso e pouco acoplado.

**Testes de Integração:** Os Testes de Integração **exercitam um subconjunto do sistema** e podem exercitar **grupos de unidades em um teste**. Eles são mais complicados de escrever e manter e **são executados mais lentamente** que os testes unitários.

**Testes ponta a ponta:** Um teste ponta a ponta **exercita o sistema usando a mesma interface que um usuário usaria**, como um navegador da web. Embora extremamente completos, os testes ponta a ponta **podem ser muito lentos e frágeis** porque usam interações simuladas do usuário em UIs potencialmente complicadas. Implemente o menor número desses testes.
# The Red, Green, Refactor Loop
Este ciclo consiste de:
1. **Vermelho:** Escreva um teste com falha para a funcionalidade desejada.
2. **Verde:** Implemente a coisa mais simples que pode funcionar para fazer o teste passar.
3. **Refatorar:** Procure oportunidades para simplificar, reduzir a duplicação ou melhorar o código de outra forma sem alterar qualquer comportamento – refatorar.
4. **Repita.**
