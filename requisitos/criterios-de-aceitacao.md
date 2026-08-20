# Critérios de Aceitação — RISC Convert

## 1. Objetivo

Este documento apresenta os critérios de aceitação das principais histórias de usuário do cenário fictício RISC Convert.

Os critérios foram escritos no formato Gherkin:

`Dado / Quando / Então`

O objetivo é transformar requisitos e histórias de usuário em comportamentos verificáveis, facilitando a validação funcional e a futura criação de casos de teste.

---

## 2. Critérios de Aceitação

### CA01 — Submissão válida de projeto

**História relacionada:** US01
**Requisitos relacionados:** RF01, RF02

```gherkin
Dado que o usuário possui um projeto em formato aceito pela plataforma
Quando realizar a submissão do projeto
Então o sistema deve receber os arquivos
E executar a validação inicial
E registrar a submissão
E informar que o projeto foi aceito para análise
```

---

### CA02 — Rejeição de projeto com entrada inválida

**História relacionada:** US02
**Requisito relacionado:** RF02

```gherkin
Dado que o usuário submete um projeto com formato ou estrutura inválida
Quando o sistema executar a validação inicial
Então a submissão não deve avançar para a etapa de conversão
E o sistema deve informar o motivo da rejeição
E permitir que o usuário realize uma nova submissão após a correção
```

---

### CA03 — Identificação de dependências incompatíveis

**Histórias relacionadas:** US03, US04
**Requisitos relacionados:** RF03, RF04

```gherkin
Dado que o projeto submetido possui dependências
Quando o sistema realizar a análise da estrutura do projeto
Então deve identificar as dependências detectadas
E registrar aquelas que não possam ser convertidas automaticamente
E disponibilizar essa informação para consulta
```

---

### CA04 — Início da conversão somente após validação

**História relacionada:** US05
**Requisito relacionado:** RF05
**Regra relacionada:** RN01

```gherkin
Dado que o projeto foi submetido com sucesso
E passou pela validação inicial
Quando o usuário solicitar o início da conversão
Então o sistema deve criar uma nova execução
E iniciar o processamento do projeto
```

---

### CA05 — Bloqueio de conversão com entrada inválida

**História relacionada:** US05
**Requisitos relacionados:** RF02, RF05
**Regra relacionada:** RN01

```gherkin
Dado que o projeto não passou pela validação inicial
Quando o usuário tentar iniciar a conversão
Então o sistema deve impedir o início do processamento
E informar que existem problemas pendentes na entrada
```

---

### CA06 — Acompanhamento do status da conversão

**História relacionada:** US06
**Requisitos relacionados:** RF06, RF07

```gherkin
Dado que existe uma conversão registrada
Quando o usuário consultar seu andamento
Então o sistema deve apresentar o estado atual da execução
E informar a etapa em processamento
```

---

### CA07 — Estados distintos da conversão

**Histórias relacionadas:** US06, US14, US15
**Requisitos relacionados:** RF07, RF15

```gherkin
Dado que uma conversão pode assumir diferentes resultados
Quando o sistema apresentar seu status
Então deve diferenciar estados de processamento, validação, conclusão com ressalvas e falha
E não deve apresentar uma conversão apenas processada como automaticamente validada
```

---

### CA08 — Registro dos logs

**História relacionada:** US07
**Requisito relacionado:** RF08

```gherkin
Dado que uma conversão está em processamento
Quando uma etapa relevante for executada
Então o sistema deve registrar o evento em log
E relacioná-lo à execução correspondente
```

---

### CA09 — Proteção de informações sensíveis nos logs

**História relacionada:** US16
**Regra relacionada:** RN09

```gherkin
Dado que uma informação sensível foi identificada durante o processamento
Quando o sistema registrar eventos em log
Então o valor sensível não deve ser armazenado em texto aberto
E deve ser mascarado quando sua referência for necessária
```

---

### CA10 — Validação de build bem-sucedida

**História relacionada:** US08
**Requisito relacionado:** RF09

```gherkin
Dado que a conversão foi concluída
E a tecnologia de destino permite execução de build
Quando o sistema realizar a validação de build
Então o resultado deve ser registrado
E deve ficar disponível no relatório da conversão
```

---

### CA11 — Falha de build

**Histórias relacionadas:** US08, US10, US14
**Requisitos relacionados:** RF09, RF11, RF15
**Regra relacionada:** RN04

```gherkin
Dado que o código convertido possui erro de build
Quando a validação for executada
Então o sistema deve registrar a falha
E a conversão não deve ser classificada como validada
E o erro deve ser apresentado para revisão técnica
```

---

### CA12 — Execução de testes automatizados

**História relacionada:** US09
**Requisito relacionado:** RF10

```gherkin
Dado que existem testes automatizados compatíveis com o projeto convertido
Quando a etapa de validação for executada
Então o sistema deve executar os testes
E registrar a quantidade de testes aprovados e reprovados
E disponibilizar o resultado no relatório
```

---

### CA13 — Projeto sem testes automatizados

**Histórias relacionadas:** US09, US13
**Requisitos relacionados:** RF10, RF14
**Lacuna relacionada:** LA09

```gherkin
Dado que o projeto convertido não possui testes automatizados disponíveis
Quando o sistema executar a etapa de validação
Então deve registrar a ausência de testes
E indicar que a validação funcional ficou limitada
E não deve considerar automaticamente a conversão como funcionalmente validada
```

---

### CA14 — Exibição de falha de validação

**História relacionada:** US10
**Requisito relacionado:** RF11

```gherkin
Dado que ocorreu uma falha durante uma etapa de validação
Quando o usuário consultar o resultado
Então o sistema deve informar qual etapa falhou
E apresentar uma mensagem relacionada ao erro
E indicar, quando possível, o item que necessita revisão
```

---

### CA15 — Preservação do progresso após interrupção recuperável

**História relacionada:** US11
**Requisito relacionado:** RF12
**Regras relacionadas:** RN06, RN07

```gherkin
Dado que uma conversão possui etapas já concluídas
Quando ocorrer uma interrupção recuperável
Então o sistema deve preservar o estado válido alcançado
E evitar o reprocessamento de etapas já concluídas quando tecnicamente possível
```

---

### CA16 — Retomada da conversão

**História relacionada:** US11
**Requisito relacionado:** RF12

```gherkin
Dado que uma conversão foi interrompida após a criação de um checkpoint válido
Quando o processamento for retomado
Então o sistema deve continuar a partir do último estado válido
E manter o histórico da execução
```

---

### CA17 — Disponibilização de artefatos

**História relacionada:** US12
**Requisito relacionado:** RF13

```gherkin
Dado que a conversão produziu artefatos disponíveis
Quando o usuário acessar o resultado da execução
Então o sistema deve permitir o download dos artefatos associados àquela conversão
```

---

### CA18 — Geração de relatório de conversão

**História relacionada:** US13
**Requisito relacionado:** RF14

```gherkin
Dado que o processamento chegou a um estado final
Quando o usuário acessar o relatório da conversão
Então o sistema deve apresentar o resultado geral
E o resultado do build, quando aplicável
E o resultado dos testes, quando aplicável
E as dependências incompatíveis identificadas
E os itens que necessitam de revisão manual
```

---

### CA19 — Conversão concluída não equivale a conversão validada

**História relacionada:** US14
**Requisito relacionado:** RF15
**Regras relacionadas:** RN03, RN10

```gherkin
Dado que todas as etapas de processamento foram concluídas
Quando ainda existirem validações técnicas pendentes
Então o sistema deve indicar que o processamento foi concluído
Mas não deve classificar a conversão como validada
```

---

### CA20 — Conversão concluída com ressalvas

**História relacionada:** US15
**Requisitos relacionados:** RF11, RF14, RF15
**Regras relacionadas:** RN05, RN14

```gherkin
Dado que o processamento foi concluído
E existem dependências incompatíveis ou falhas não bloqueantes
Quando o sistema determinar o status final
Então deve classificar a execução como "Concluída com ressalvas"
E apresentar os itens que exigem intervenção manual
```

---

### CA21 — Bloqueio de envio de segredo ao serviço externo

**História relacionada:** US16
**Regra relacionada:** RN02
**Lacuna relacionada:** LA14

```gherkin
Dado que uma possível credencial, token ou chave foi identificada no projeto
Quando o sistema preparar conteúdo para envio ao serviço externo de IA
Então o envio deve ser bloqueado
E o usuário deve ser informado sobre a necessidade de tratamento da informação
```

---

### CA22 — Rastreabilidade por identificador único

**História relacionada:** US17
**Requisitos relacionados:** RF08, RF14
**Regra relacionada:** RN08

```gherkin
Dado que uma nova conversão foi criada
Quando o sistema registrar sua execução
Então deve gerar um identificador único
E relacionar a esse identificador os logs, validações, status e artefatos produzidos
```

---

### CA23 — Falha temporária do serviço de IA

**História relacionada:** US18
**Requisitos relacionados:** RF06, RF08, RF12
**Regras relacionadas:** RN11, RN12

```gherkin
Dado que uma conversão está utilizando o serviço externo de IA
Quando ocorrer uma falha temporária de comunicação
Então o sistema deve registrar o erro
E preservar o estado atual da execução
E aplicar a política de novas tentativas configurada
```

---

### CA24 — Falha persistente do serviço de IA

**História relacionada:** US18
**Requisitos relacionados:** RF08, RF12
**Regras relacionadas:** RN11, RN12

```gherkin
Dado que ocorreram falhas consecutivas na comunicação com o serviço externo de IA
E o limite configurado de tentativas foi atingido
Quando a próxima tentativa não puder ser realizada
Então o sistema deve interromper o processamento
E preservar os resultados já concluídos
E registrar a causa da interrupção
E informar o usuário
```

---

## 3. Critérios não definidos por falta de informação

Alguns critérios de aceitação não foram especificados com valores quantitativos porque o cenário ainda apresenta lacunas.

Exemplos:

* tempo máximo de conversão;
* tamanho máximo do projeto;
* quantidade de conversões simultâneas;
* número máximo de tentativas;
* período de retenção;
* percentual mínimo de disponibilidade.

Esses valores só deverão ser incorporados aos critérios de aceitação após validação com os stakeholders.

---

## 4. Relação entre critérios e testes

Os critérios de aceitação podem ser utilizados posteriormente como base para derivação de casos de teste.

Exemplo:

`US11 → CA15 / CA16 → Casos de teste de interrupção e retomada`

Outro exemplo:

`US14 → CA11 / CA19 → Casos de teste relacionados à validação do resultado`

Essa relação contribui para manter rastreabilidade entre requisito, especificação e validação.

---

## 5. Papel da Inteligência Artificial Generativa

A IA Generativa foi utilizada como apoio para transformar histórias de usuário em cenários verificáveis no formato Dado–Quando–Então.

As sugestões foram revisadas para evitar:

* critérios baseados em funcionalidades não definidas;
* números sem fonte;
* regras que ainda dependem de decisão;
* cenários excessivamente genéricos;
* critérios subjetivos ou impossíveis de testar.

Sugestões com valores como tempo máximo de resposta, número exato de tentativas ou período fixo de retenção não foram incorporadas como fatos.

Esses pontos permaneceram registrados como lacunas.

---

## 6. Considerações finais

Os critérios de aceitação tornam as histórias de usuário do RISC Convert mais objetivas e verificáveis.

O uso do formato Gherkin facilita o entendimento entre negócio, desenvolvimento e QA e cria uma base para a futura elaboração de casos de teste.

A Inteligência Artificial Generativa acelerou a criação inicial dos cenários, mas a revisão humana permaneceu necessária para garantir que nenhuma decisão não validada fosse transformada em critério definitivo.
