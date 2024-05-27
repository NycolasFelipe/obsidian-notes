Definimos um contrato de API como um **acordo formal entre um fornecedor de software e um consumidor** que comunica abstratamente como interagir entre si. Este contrato define **como os provedores de API e os consumidores interagem**, como são as trocas de dados e como comunicar casos de sucesso e falha.

O provedor e os consumidores não precisam compartilhar a mesma linguagem de programação, **apenas os mesmos contratos de API**.

Exemplo de contrato de API:
```
Request
	URI: /cards/{id}
	HTTP Verb: GET
	Body: None

Response:
	HTTP Status:
		200 OK if the user is authorized and the card was successfully retrieved
		401 UNAUTHORIZED if the user is unauthenticated or unauthorized
		404 NOT FOUND if the user is authenticated and authorized but the card            cannot be found
	Response Body Type: JSON
	Example Response Body:
		{
			"id": 99,
			"amount": 123.45
		}
```
## Por que contratos de API são importantes?
Os contratos de API são importantes porque **comunicam o comportamento de uma API REST**. Eles fornecem detalhes específicos sobre os dados que estão sendo serializados (ou desserializados) para cada comando e parâmetro sendo trocados. 

Os contratos de API são escritos de forma que possam ser facilmente traduzidos em funcionalidade de provedor e consumidor de API e testes automatizados correspondentes. 