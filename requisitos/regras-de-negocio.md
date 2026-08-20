# Regras de Negócio — RISC Convert

## 1. Objetivo

Este documento apresenta as principais regras de negócio identificadas para o cenário fictício RISC Convert.

As regras de negócio definem condições, restrições e comportamentos que devem ser respeitados durante o processo de submissão, análise, conversão, validação e disponibilização dos artefatos gerados.

---

## 2. Regras de Negócio

### RN01 — Uma conversão só pode iniciar após validação da entrada

O processo de conversão só poderá ser iniciado após a validação inicial do projeto submetido.

Caso o projeto apresente estrutura inválida, arquivos incompatíveis ou ausência de conteúdo necessário para análise, a conversão não deverá prosseguir.

---

### RN02 — Projetos com informações sensíveis devem ser tratados antes do processamento externo

Caso sejam identificadas credenciais, tokens, chaves de API ou outras informações sensíveis no projeto submetido, o envio do conteúdo para um serviço externo de Inteligência Artificial deverá ser bloqueado até que essas informações sejam removidas ou mascaradas.

---

### RN03 — A conclusão do processamento não implica validação da conversão

Uma conversão que tenha concluído todas as etapas de processamento não deve ser automaticamente considerada validada.

O status da conversão deverá considerar separadamente:

* conclusão do processamento;
* resultado do build;
* resultado dos testes;
* existência de dependências incompatíveis;
* necessidade de revisão técnica.

---

### RN04 — Falhas críticas impedem a classificação como conversão validada

Uma conversão não poderá receber status de validada quando existir pelo menos uma falha crítica identificada durante:

* compilação ou build;
* testes obrigatórios;
* análise de segurança;
* validação de dependências;
* comparação funcional, quando aplicável.

---

### RN05 — Dependências incompatíveis devem ser explicitamente registradas

Sempre que uma biblioteca, componente ou dependência não puder ser convertida automaticamente, o sistema deverá registrar essa condição no resultado da conversão.

A conversão poderá ser concluída com ressalvas, desde que o usuário seja informado sobre a necessidade de intervenção manual.

---

### RN06 — O estado da conversão deve ser preservado em caso de falha recuperável

Quando ocorrer uma falha temporária ou recuperável, as etapas concluídas com sucesso deverão permanecer registradas.

O sistema deverá tentar continuar o processamento a partir do último estado válido sempre que tecnicamente possível.

---

### RN07 — Reprocessamento desnecessário deve ser evitado

Etapas concluídas e consideradas válidas não devem ser executadas novamente durante uma retomada, exceto quando houver alteração no código de entrada, mudança na configuração da conversão ou invalidação do resultado anterior.

---

### RN08 — Toda conversão deve possuir rastreabilidade

Cada execução deve possuir um identificador único que permita relacionar:

* projeto de origem;
* configuração utilizada;
* data e horário;
* etapas executadas;
* logs;
* falhas;
* validações;
* resultado final;
* artefatos gerados.

---

### RN09 — Logs não devem expor informações sensíveis

Credenciais, tokens, chaves ou segredos identificados durante o processamento não devem ser armazenados em texto aberto nos logs.

Quando necessário para rastreabilidade, essas informações deverão ser mascaradas.

---

### RN10 — Artefatos gerados por IA exigem revisão técnica

Os artefatos produzidos pela conversão não devem ser classificados como prontos para produção sem revisão humana.

A plataforma deverá informar explicitamente que o resultado gerado necessita de validação técnica antes de ser utilizado em ambiente produtivo.

---

### RN11 — Falhas de serviço externo não devem ser tratadas como falha definitiva imediatamente

Quando uma falha estiver relacionada à indisponibilidade temporária do serviço externo de IA, a conversão não deverá ser encerrada imediatamente como falha definitiva.

O sistema deverá aplicar a política de novas tentativas definida para o ambiente antes de finalizar a execução como erro.

---

### RN12 — Novas tentativas devem possuir limite

O sistema não poderá realizar tentativas indefinidas de comunicação com o serviço externo de IA.

A quantidade máxima de tentativas deverá ser configurável.

O valor exato ainda depende de definição dos responsáveis pelo projeto.

---

### RN13 — Cada execução deve manter seus próprios artefatos e registros

Arquivos, logs, resultados e artefatos de uma conversão não devem ser misturados com informações de outras execuções.

Cada conversão deverá possuir contexto independente.

---

### RN14 — O usuário deve ser informado sobre conversões concluídas com ressalvas

Quando o processamento for concluído, mas existirem dependências incompatíveis, falhas não críticas ou itens que exijam intervenção manual, o resultado deverá ser classificado como:

`Concluída com ressalvas`

O relatório deverá informar quais pontos precisam de revisão.

---

### RN15 — O resultado da conversão deve permanecer associado à entrada utilizada

Os artefatos gerados devem permanecer vinculados à versão do projeto que originou a conversão.

Caso uma nova versão do código seja submetida, ela deverá originar uma nova execução ou nova versão de conversão.

---

## 3. Regras ainda pendentes de definição

Algumas regras de negócio foram identificadas durante a análise, porém não possuem informações suficientes para serem definidas como definitivas.

### Limite de tamanho dos projetos

Ainda não foi definido o tamanho máximo permitido para os projetos submetidos.

---

### Tecnologias suportadas

Ainda não foi definida uma lista definitiva de:

* linguagens de origem;
* frameworks de origem;
* tecnologias de destino;
* combinações de conversão suportadas.

---

### Número máximo de tentativas de conversão

Foi identificada a necessidade de limitar as novas tentativas, porém o número exato ainda não foi definido.

---

### Critério final de validação

Ainda é necessário definir se determinadas falhas não críticas permitem que a conversão seja classificada como validada ou apenas como concluída com ressalvas.

---

### Política de retenção

Ainda não foram definidos:

* período de armazenamento do projeto original;
* período de armazenamento dos artefatos convertidos;
* período de retenção dos logs.

---

### Cancelamento de conversão

Ainda deverá ser definido:

* se o usuário poderá cancelar uma conversão em andamento;
* em quais etapas o cancelamento será permitido;
* quais artefatos deverão ser preservados após o cancelamento.

---

## 4. Relação entre regras de negócio e requisitos

As regras de negócio deste documento complementam os requisitos funcionais e não funcionais.

Por exemplo:

* o **RF05** determina que o sistema deve iniciar uma conversão;
* a **RN01** determina em qual condição essa conversão pode começar.

Outro exemplo:

* o **RF13** determina que os artefatos devem ser disponibilizados;
* a **RN10** determina que esses artefatos não podem ser tratados automaticamente como prontos para produção.

Essa separação permite distinguir o comportamento funcional da plataforma das condições que regulam esse comportamento.

---

## 5. Uso da Inteligência Artificial Generativa

A IA Generativa foi utilizada como apoio para identificar possíveis regras a partir dos requisitos do cenário.

Durante a revisão, algumas sugestões foram modificadas ou mantidas como pendências quando dependiam de decisões que não estavam definidas.

Por exemplo, sugestões como:

* limite fixo de tamanho de projeto;
* número exato de tentativas;
* período específico de retenção;
* quantidade mínima de testes necessários;

não foram consideradas regras definitivas por falta de informação suficiente.

Esses pontos foram registrados como decisões pendentes, evitando transformar suposições da IA em regras de negócio.

---

## 6. Considerações finais

As regras de negócio do RISC Convert definem condições que devem ser respeitadas durante a execução das principais funcionalidades da plataforma.

A separação entre requisitos e regras permite reduzir ambiguidades e evita que decisões ainda não validadas sejam incorporadas como comportamentos obrigatórios do sistema.
