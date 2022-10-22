# Documentação não oficial da API DivulgaCandContas

O Tribunal Superior Eleitoral disponibiliza os dados sobre candidaturas em
eleições de três formas:

1. Para consulta pela web, no sistema
   [DivulgaCandContas](https://divulgacandcontas.tse.jus.br/divulga/);
2. Para download, em arquivos CSV, pelo
   [repositório de dados eleitorais](https://www.tse.jus.br/eleicoes/estatisticas/repositorio-de-dados-eleitorais-1/repositorio-de-dados-eleitorais);
3. Por uma API do tipo REST.

A API é usada pelo sistema que faz a consulta pela web. Entretanto, ela não
está documentada. Tentativas de obter a documentação oficial junto ao TSE não
lograram êxito. Por isso, decidimos começar a criar uma documentação não
oficial para ajudar a quem mais esteja tentando utilizá-la.

## Como usar

Para usar a API, consulte a documentação no formato
[Open API 2.0](https://swagger.io/specification/v2/). Para mais informações
sobre o padrão Open API, consulte o site [swagger.io](https://swagger.io/).

A documentação está no arquivo
[divulgacandcontas-swagger.yaml](docs/divulgacandcontas-swagger.yaml). Além disso,
o arquivo [divulgacandcontas.http](examples/divulgacandcontas.http) possui alguns
exemplos de consultas prontas para uso.

**Mas atenção:** antes de usar a API, tome alguns cuidados:
* confira se a sua necessidade de dados pode ser satisfeita pelos downloads
  de dados disponíveis no
  [repositório de dados eleitorais](https://www.tse.jus.br/eleicoes/estatisticas/repositorio-de-dados-eleitorais-1/repositorio-de-dados-eleitorais)
  do TSE. Use a API apenas se os dados não estiverem disponíveis lá (por
  exemplo, os planos de governo dos candidatos, como nos [exemplos](examples))
  ou você está querendo informações atualizadas apenas por um recorte dos
  dados (ex.: candidatos de um município específico).
* Se decidir usar a API, coloque um intervalo de tempo entre as consultas,
  para não sobrecarregar os servidores do TSE. Dessa maneira evitamos que ela
  seja retirada do ar e reduz o risco do seu IP ser bloqueado na API.

### Experimentando com chamadas à API

Para consultar a definição da API acesse o página publicada [aqui](https://xaviersjc.github.io/divulgacandcontas-doc/)

Todavia, a API do TSE impedirá as consultas de funcionar pelo navegador, atualmente a API não suporta
*[Cross Origin Resource Sharing](https://pt.wikipedia.org/wiki/Cross-origin_resource_sharing)*
(CORS), o que faz com que o navegador bloqueie chamadas à API a partir de
outros domíníos.

Uma possível solução, para quem usa Firefox, é instalar a extensão
[CORS Everywhere](https://addons.mozilla.org/en-US/firefox/addon/cors-everywhere/)
e configurar o "*activation whitelist*" para `/^https:\/\/editor.swagger.io/`.
Ative a extensão na aba do editor de Swagger para que as chamadas à API passem
a funcionar no Firefox.

Também é possível utilizar o site [Swagger Inspector](https://inspector.swagger.io/builder), no canto superior esquerdo
em "Definition" fornecer a URL que aponta para a documentação deste repositorio. Essa [URL](https://raw.githubusercontent.com/XavierSJC/divulgacandcontas-doc/ConvertToYamlAndPrepareToPublish/docs/divulgacandcontas-swagger.yaml)

Você pode encontrar exemplos de scripts para acessar essa API no diretório
[`examples`](examples/).

## Como contribuir

Essa documentação está em construção e contém apenas uma pequena fração do
que está disponível na API. Caso você encontre alguma outra chamada à API que
seja útil para você, não hesite em enviar o *pull request* com a sua
complementação.
