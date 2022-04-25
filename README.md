# Testes Automatizados em Node [EM CONSTRUÇÃO]

Tutorial para quem quer começar a construir software mais confiável e de forma mais eficiente.

## Índice

- [Testes Automatizados, Testes Unitários e TDD](#testes-automatizados-unitários-e-tdd-são-a-mesma-coisa)
    - [Testes Automatizados](#testes-automatizados)
    - [Testes Unitários e Pirâmide de Testes](#testes-unitários-e-pirâmide-de-testes)
    - [TDD](#tdd)
- [Testes em JavaScript](#testes-em-javascript)
    - [Antes de Começar](#antes-de-começar)
        - [Conhecimentos Necessários](#conhecimentos-necessários)
        - [Requisitos Técnicos](#requisitos-técnicos)

## Testes automatizados, unitários e TDD: são a mesma coisa?

Definitivamente não. Quem não escreve testes costuma tratar esses termos como sinônimos, mas definitivamente não são. Um bom ponto para começar a entender um pouco mais sobre testes de software é entender a diferença entre eles. Este é um guia (muito) introdutório, para que comecem a se familiarizar com os termos e práticas. Futuramente espero acrescentar referências para que possam se aprofundar sobre o tema (ou se você tiver indicações, sua contribuição será muito bem vinda :))

### Testes Automatizados

Imagina-se que qualquer pessoa que desenvolva software vá testar o projeto "pra ver se tá funcionando". Esse tipo de teste é chamado de **teste manual**. É o tipo de teste que mais vemos, pois no curto prazo e em projetos simples ele é mais rápido e barato. Acontece que conforme o projeto escala em tamanho e complexidade, realizar testes manuais para cada alteração é impraticável. Para isso (e mais) existem os testes automatizados! São códigos que executamos, separadamente do código de produção, para verificarmos comportamentos esperados - de sucesso e de erro. Com eles podemos ter mais tranquilidade em fazer alterações, pois basta dar um comando para executar os testes e verificar que nada foi inesperadamente alterado.

### Testes Unitários e Pirâmide de Testes

Existem, a grosso modo, três tipos diferentes de testes automatizados: unitários, de integração e de ponta a ponta (ou end-to-end ou e2e). Os testes unitários são os mais simples, rápidos e baratos de serem desenvolvidos e executados. Testam funcionalidades em isolamento, e devem contemplar o maior número de casos possíveis (que façam sentido).
Os testes de integração (que envolvem duas ou mais camadas da aplicação) geralmente envolvem fluxos mais caros, como consultas a bancos de dados, e por isso devem ser limitados aos casos críticos do negócio.
Já os testes e2e são os mais caros, pois executam um ou mais fluxos inteiros, desde a interface da aplicação (api, cli, etc) até a persistência dos dados. Muitas vezes são complexos de serem escritos e demoram bastante para serem executados. Devem ser limitados aos comportamentos mais comuns e/ou críticos do sistema.

### TDD

Escrever testes automatizados não é aplicar TDD! TDD (Test Driven Development, ou Desenvolvimento Orientado a Testes) é uma técnica de programação, creditada a Kent Beck como parte da sua metodologia *Extreme Programming*, em que o desenvolvedor começa escrevendo (programando) os casos de teste de uma funcionalidade, para depois escrever a funcionalidade. Segue o conceito do "fail, pass, refactor", em que primeiro escrevemos um teste que irá falhar (pois a implementação ainda não foi feita), depois o fazemos passar "de qualquer jeito", depois refatoramos para que a aplicação exiba o comportamento desejado.

## Testes em JavaScript

Até a versão estável atual do Node (16), não temos um runner nativo para testes. Essa funcionalidade está em fase experimental no Node 18 (o [módulo `node:test`](https://nodejs.org/api/test.html#test-runner)), e deve ser lançada em outubro 2022. Por enquanto, usamos libs de terceiros para facilitar a visualização dos resultados dos testes. As mais comuns são [Jest](https://jestjs.io/) e [Mocha](https://mochajs.org/). Utilizaremos a segunda nesse repositório, por possuir suporte nativo a ESM (`import` em vez de `require`). A intenção aqui é mostrar primeiramente como escrever testes unitários para funções simples, e futuramente desenvolver uma API com todos os testes relevantes (unitários, de integração e e2e).

## Antes de começar

### Conhecimentos necessários

Para começar com testes unitários, conhecimento básico de JavaScript será suficiente. Familiaridade com Node vai facilitar o processo, mas não é determinante. Para a API será importante conhecimentos de API REST. Nos testes de integração e e2e utilizaremos Docker para criação de containeres onde rodaremos os testes (você conseguirá acompanhar apenas copiando os arquivos do Docker).

### Requisitos técnicos

- [Node (versão recomendada: 16)](https://nodejs.org/en/download/);
- [Mocha](https://www.npmjs.com/package/mocha) recomendado instalação global;
- [Docker](https://docs.docker.com/engine/install/) **somente para testes de integração e e2e**
