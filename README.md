# RISC Convert

## Sobre o projeto

O RISC Convert é uma plataforma web fictícia criada para fins acadêmicos, voltada à modernização de sistemas legados com apoio de Inteligência Artificial Generativa.

A solução permite que equipes de desenvolvimento submetam o código-fonte de uma aplicação antiga para análise e conversão automatizada. A plataforma utiliza IA Generativa para apoiar a transformação do código para uma tecnologia mais moderna, realizando etapas de validação antes de disponibilizar os artefatos convertidos para revisão e download.

O objetivo do projeto é reduzir o esforço manual envolvido em processos de modernização de software, mantendo mecanismos de validação, rastreabilidade, segurança e revisão humana.

## Fluxo da solução

O processo de conversão ocorre nas seguintes etapas:

1. Envio do código-fonte da aplicação;
2. Análise da estrutura do projeto;
3. Identificação de componentes e dependências;
4. Conversão do código com apoio de IA Generativa;
5. Validação automática dos artefatos gerados;
6. Registro de logs e possíveis erros;
7. Revisão técnica;
8. Disponibilização dos artefatos para download.

Fluxo resumido:

`Upload do projeto → Análise → Conversão por IA → Validação → Revisão → Download`

## Arquitetura fictícia

Para o cenário acadêmico, foi considerada a seguinte arquitetura:

- Frontend web em React;
- Backend desenvolvido em Python com FastAPI;
- Banco de dados PostgreSQL;
- Processamento assíncrono das conversões;
- Integração com um serviço externo de Inteligência Artificial Generativa;
- Pipeline de validação automática;
- Registro de logs das execuções;
- Armazenamento temporário dos artefatos gerados.

## Objetivo

Desenvolver uma plataforma capaz de apoiar a modernização de aplicações legadas, utilizando Inteligência Artificial Generativa para reduzir o esforço manual de conversão de código, sem eliminar a necessidade de testes, validação técnica e revisão humana.

## Gerenciamento de riscos

Como parte da atividade da disciplina de Gerência de Projetos de Software Apoiada por Inteligência Artificial Generativa, foram analisados riscos relacionados a:

- qualidade do código convertido;
- incompatibilidade de componentes e dependências;
- desempenho e tempo de processamento;
- dependência de serviços externos de IA;
- segurança e proteção de informações;
- custos de processamento;
- rastreabilidade;
- continuidade das conversões;
- validação dos resultados gerados por IA.

A documentação detalhada está disponível na pasta `docs`.

## Documentação

- [Gestão de riscos](docs/gestao-de-riscos.md)
- [Plano de resposta aos riscos](docs/plano-de-resposta.md)
- [Plano de comunicação](docs/plano-de-comunicacao.md)
- [Uso de IA Generativa](docs/uso-de-ia-generativa.md)

## Aviso acadêmico

Este repositório foi desenvolvido exclusivamente para fins acadêmicos.

O RISC Convert é um cenário fictício inspirado em situações comuns de projetos de modernização de software. Todos os nomes, métricas, tecnologias, riscos, equipes e demais informações apresentadas foram criados ou adaptados para esta atividade e não representam dados de organizações, clientes ou projetos reais.
