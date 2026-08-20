# Histórias de Usuário — RISC Convert

## 1. Objetivo

Este documento apresenta as histórias de usuário definidas para o cenário fictício RISC Convert.

As histórias foram estruturadas no formato:

`Como [tipo de usuário], quero [ação], para [benefício].`

Cada história foi relacionada aos requisitos funcionais correspondentes para facilitar a rastreabilidade entre análise e especificação.

---

## 2. Perfis considerados

Para as histórias de usuário, foram considerados os seguintes perfis:

* Usuário da plataforma;
* Desenvolvedor;
* Líder Técnico;
* QA;
* Engenheiro de Plataforma;
* Especialista de Segurança.

---

## 3. Histórias de Usuário

### US01 — Submeter projeto para conversão

**Como** usuário da plataforma,
**quero** submeter um projeto de software,
**para** iniciar o processo de análise e conversão para uma tecnologia de destino.

**Requisitos relacionados:** RF01, RF02

---

### US02 — Receber retorno sobre projeto inválido

**Como** usuário da plataforma,
**quero** ser informado quando o projeto submetido não atender aos critérios mínimos de entrada,
**para** corrigir os problemas antes de iniciar a conversão.

**Requisitos relacionados:** RF02

---

### US03 — Visualizar a análise do projeto

**Como** desenvolvedor,
**quero** visualizar a estrutura, os componentes e as dependências identificadas no projeto,
**para** compreender quais elementos serão considerados durante a conversão.

**Requisitos relacionados:** RF03, RF04

---

### US04 — Identificar dependências incompatíveis

**Como** desenvolvedor,
**quero** ser informado sobre bibliotecas ou componentes que não podem ser convertidos automaticamente,
**para** planejar as adaptações manuais necessárias.

**Requisitos relacionados:** RF04

---

### US05 — Iniciar uma conversão

**Como** usuário da plataforma,
**quero** iniciar a conversão de um projeto previamente validado,
**para** obter uma versão adaptada para a tecnologia de destino.

**Requisitos relacionados:** RF05

**Regra relacionada:** RN01

---

### US06 — Acompanhar o progresso da conversão

**Como** usuário da plataforma,
**quero** acompanhar o status do processamento,
**para** saber em qual etapa a conversão se encontra.

**Requisitos relacionados:** RF06, RF07

---

### US07 — Consultar os logs da conversão

**Como** desenvolvedor,
**quero** consultar os logs do processamento,
**para** identificar erros, avisos e etapas executadas durante a conversão.

**Requisitos relacionados:** RF08

---

### US08 — Validar o build do projeto convertido

**Como** desenvolvedor,
**quero** que o sistema execute o build ou compilação do projeto convertido,
**para** identificar problemas técnicos antes da revisão final.

**Requisitos relacionados:** RF09

---

### US09 — Executar testes automatizados

**Como** QA,
**quero** executar testes automatizados sobre o projeto convertido,
**para** identificar regressões ou comportamentos inesperados.

**Requisitos relacionados:** RF10

---

### US10 — Visualizar falhas de validação

**Como** desenvolvedor,
**quero** receber informações claras sobre falhas ocorridas durante a validação,
**para** saber quais pontos precisam de correção ou revisão manual.

**Requisitos relacionados:** RF11

---

### US11 — Retomar conversão interrompida

**Como** usuário da plataforma,
**quero** que uma conversão interrompida possa continuar a partir do último estado válido,
**para** evitar o reprocessamento completo do projeto.

**Requisitos relacionados:** RF12

**Regras relacionadas:** RN06, RN07

---

### US12 — Baixar os artefatos convertidos

**Como** usuário da plataforma,
**quero** baixar os artefatos gerados ao final da conversão,
**para** revisá-los e utilizá-los nas próximas etapas de modernização do software.

**Requisitos relacionados:** RF13

---

### US13 — Consultar relatório da conversão

**Como** Líder Técnico,
**quero** visualizar um relatório com os resultados da conversão,
**para** avaliar build, testes, incompatibilidades, falhas e itens que necessitam revisão.

**Requisitos relacionados:** RF14

---

### US14 — Diferenciar processamento concluído de conversão validada

**Como** Líder Técnico,
**quero** distinguir uma conversão apenas processada de uma conversão tecnicamente validada,
**para** evitar que código gerado seja interpretado como pronto para produção sem revisão adequada.

**Requisitos relacionados:** RF15

**Regras relacionadas:** RN03, RN04, RN10

---

### US15 — Ser informado sobre conversões concluídas com ressalvas

**Como** usuário da plataforma,
**quero** visualizar quando uma conversão foi concluída com ressalvas,
**para** identificar componentes ou falhas que ainda exigem intervenção manual.

**Requisitos relacionados:** RF04, RF11, RF14, RF15

**Regras relacionadas:** RN05, RN14

---

### US16 — Bloquear processamento de código com segredos identificados

**Como** Especialista de Segurança,
**quero** que o sistema identifique e bloqueie o processamento externo quando forem encontrados segredos no código,
**para** reduzir o risco de exposição de informações sensíveis.

**Requisitos relacionados:** RF02

**Regras relacionadas:** RN02, RN09

---

### US17 — Preservar rastreabilidade da conversão

**Como** Líder Técnico,
**quero** que cada conversão possua um identificador único e histórico associado,
**para** relacionar entrada, logs, validações e artefatos produzidos.

**Requisitos relacionados:** RF08, RF14

**Regra relacionada:** RN08

---

### US18 — Tratar indisponibilidade do serviço externo de IA

**Como** Engenheiro de Plataforma,
**quero** que falhas temporárias do serviço externo de IA sejam tratadas de forma controlada,
**para** evitar perda de progresso e encerramentos desnecessários da conversão.

**Requisitos relacionados:** RF06, RF08, RF12

**Regras relacionadas:** RN11, RN12

---

## 4. Histórias dependentes de decisões pendentes

Algumas histórias potenciais não foram formalizadas como requisito definitivo porque dependem de lacunas ainda abertas.

### Cancelar uma conversão

Uma história para cancelamento não foi criada como definitiva porque ainda não foi estabelecido:

* se o usuário poderá cancelar uma conversão;
* em quais etapas;
* quais artefatos serão preservados;
* se será possível retomar posteriormente.

**Lacuna relacionada:** LA10

---

### Selecionar tecnologia de origem e destino

A funcionalidade depende da definição das tecnologias oficialmente suportadas pela plataforma.

**Lacunas relacionadas:** LA01 e LA02

---

### Consultar histórico por período definido

Existe necessidade de histórico, mas o período de retenção ainda não foi estabelecido.

**Lacuna relacionada:** LA07

---

## 5. Exemplo de rastreabilidade

Exemplo de relação entre diferentes artefatos:

`RF12 → US11 → RN06/RN07 → Critérios de Aceitação`

Nesse exemplo:

* o **RF12** determina que o sistema deve preservar o progresso;
* a **US11** representa a necessidade do usuário;
* as **RN06 e RN07** determinam as condições para retomada;
* os critérios de aceitação serão utilizados posteriormente para transformar esse comportamento em cenários testáveis.

---

## 6. Papel da Inteligência Artificial Generativa

A IA Generativa foi utilizada como apoio para transformar requisitos descritos de forma técnica em histórias orientadas ao valor para diferentes usuários.

Durante a análise, algumas sugestões foram modificadas para evitar histórias excessivamente técnicas ou que não apresentassem benefício claro para um ator.

Também foram descartadas histórias baseadas em funcionalidades ainda não definidas no cenário.

Por exemplo, a IA sugeriu histórias relacionadas a:

* cancelamento da conversão;
* seleção de linguagens específicas;
* retenção por determinado período;
* notificações automáticas por e-mail.

Como essas informações não estavam definidas, elas não foram incorporadas como histórias definitivas.

---

## 7. Considerações finais

As histórias de usuário permitem representar os requisitos do RISC Convert a partir da perspectiva de seus diferentes perfis de utilização.

A associação com requisitos funcionais, regras de negócio e lacunas contribui para manter rastreabilidade e evitar que funcionalidades ainda não validadas sejam incorporadas indevidamente ao escopo.
