# Matriz de Rastreabilidade — RISC Convert

## 1. Objetivo

Este documento apresenta a matriz de rastreabilidade dos requisitos do cenário fictício RISC Convert.

A matriz tem como objetivo relacionar os diferentes artefatos produzidos durante a análise e especificação, permitindo acompanhar a origem, o detalhamento e a validação de cada requisito.

A rastreabilidade considerada neste projeto segue, de forma geral, a relação:

`Requisito → Regra de Negócio → História de Usuário → Caso de Uso → Critério de Aceitação`

Quando houver alguma definição ainda pendente, a respectiva lacuna também é indicada.

---

## 2. Matriz de rastreabilidade principal

| Requisito | Descrição resumida                     | Regra(s) relacionada(s) | Lacuna(s)        | História(s)      | Caso(s) de Uso   | Critério(s) de Aceitação     |
| --------- | -------------------------------------- | ----------------------- | ---------------- | ---------------- | ---------------- | ---------------------------- |
| RF01      | Submeter projeto                       | —                       | —                | US01             | UC01             | CA01                         |
| RF02      | Validar projeto submetido              | RN01, RN02              | LA14             | US01, US02, US16 | UC01             | CA01, CA02, CA05, CA21       |
| RF03      | Analisar estrutura do projeto          | —                       | LA01, LA02       | US03             | UC02             | CA03                         |
| RF04      | Identificar dependências incompatíveis | RN05                    | LA12             | US03, US04, US15 | UC02, UC03       | CA03, CA20                   |
| RF05      | Iniciar conversão                      | RN01                    | —                | US05             | UC02             | CA04, CA05                   |
| RF06      | Processar projeto em etapas            | RN06, RN11              | LA06             | US06, US18       | UC02, UC03       | CA06, CA23                   |
| RF07      | Exibir progresso da conversão          | RN03, RN14              | —                | US06, US14, US15 | UC03             | CA06, CA07                   |
| RF08      | Registrar logs                         | RN08, RN09              | —                | US07, US17, US18 | UC02, UC03       | CA08, CA09, CA22, CA23, CA24 |
| RF09      | Executar validação de build            | RN03, RN04              | LA08             | US08, US10, US14 | UC04             | CA10, CA11                   |
| RF10      | Executar testes automatizados          | RN03, RN04              | LA08, LA09       | US09, US13       | UC04             | CA12, CA13                   |
| RF11      | Apresentar falhas de validação         | RN04, RN14              | LA08, LA11       | US10, US15       | UC03, UC04, UC05 | CA11, CA14, CA20             |
| RF12      | Preservar progresso da conversão       | RN06, RN07, RN11        | LA06             | US11, US18       | UC02             | CA15, CA16, CA23, CA24       |
| RF13      | Disponibilizar artefatos convertidos   | RN10, RN15              | LA07             | US12             | UC05             | CA17                         |
| RF14      | Disponibilizar relatório da conversão  | RN08, RN14              | LA08             | US13, US15, US17 | UC04, UC05       | CA18, CA20, CA22             |
| RF15      | Diferenciar concluída de validada      | RN03, RN04, RN10, RN14  | LA08, LA11, LA13 | US14, US15       | UC03, UC04, UC05 | CA07, CA11, CA19, CA20       |

---

## 3. Rastreabilidade das regras de negócio

| Regra | Descrição resumida                                         | Requisitos relacionados | Histórias relacionadas | Casos de Uso relacionados |
| ----- | ---------------------------------------------------------- | ----------------------- | ---------------------- | ------------------------- |
| RN01  | Conversão só inicia após validação                         | RF02, RF05              | US02, US05             | UC01, UC02                |
| RN02  | Segredos devem ser tratados antes do processamento externo | RF02                    | US16                   | UC01                      |
| RN03  | Conclusão não implica validação                            | RF07, RF09, RF10, RF15  | US14                   | UC03, UC04, UC05          |
| RN04  | Falhas críticas impedem validação                          | RF09, RF10, RF11, RF15  | US08, US09, US10, US14 | UC04                      |
| RN05  | Dependências incompatíveis devem ser registradas           | RF04, RF11              | US04, US15             | UC02, UC03, UC05          |
| RN06  | Estado deve ser preservado em falha recuperável            | RF06, RF12              | US11, US18             | UC02                      |
| RN07  | Reprocessamento desnecessário deve ser evitado             | RF12                    | US11                   | UC02                      |
| RN08  | Toda conversão deve possuir rastreabilidade                | RF08, RF14              | US17                   | UC02                      |
| RN09  | Logs não devem expor segredos                              | RF08                    | US16                   | UC01                      |
| RN10  | Artefatos gerados por IA exigem revisão                    | RF13, RF15              | US12, US14             | UC04, UC05                |
| RN11  | Falha externa temporária não é imediatamente definitiva    | RF06, RF12              | US18                   | UC02                      |
| RN12  | Tentativas devem possuir limite                            | RF12                    | US18                   | UC02                      |
| RN13  | Execuções devem manter contexto independente               | RF08, RF13, RF14        | US17                   | UC02, UC05                |
| RN14  | Ressalvas devem ser comunicadas ao usuário                 | RF07, RF11, RF14, RF15  | US15                   | UC03, UC04, UC05          |
| RN15  | Resultado deve permanecer associado à entrada              | RF13, RF14              | US12, US17             | UC05                      |

---

## 4. Rastreabilidade das lacunas

| Lacuna | Descrição resumida                            | Artefatos afetados                                      |
| ------ | --------------------------------------------- | ------------------------------------------------------- |
| LA01   | Tecnologias de origem suportadas              | RF03, futuras histórias de seleção de tecnologia        |
| LA02   | Tecnologias de destino suportadas             | RF03, futuras histórias de seleção de tecnologia        |
| LA03   | Tamanho máximo do projeto                     | RNF de desempenho e infraestrutura                      |
| LA04   | Tempo máximo de processamento                 | RNF de desempenho                                       |
| LA05   | Quantidade de conversões simultâneas          | RNF de escalabilidade                                   |
| LA06   | Número máximo de tentativas                   | RF06, RF12, RN11, RN12, US18                            |
| LA07   | Política de retenção                          | RF13, histórico e armazenamento                         |
| LA08   | Critério definitivo para conversão validada   | RF09, RF10, RF11, RF14, RF15, UC04                      |
| LA09   | Tratamento de projetos sem testes             | RF10, US09, UC04, CA13                                  |
| LA10   | Cancelamento de conversão                     | Potencial história e caso de uso ainda não formalizados |
| LA11   | Falha versus concluída com ressalvas          | RF11, RF15, UC04, UC05                                  |
| LA12   | Critério de incompatibilidade de dependências | RF04, US04                                              |
| LA13   | Responsável pela revisão final                | RF15, US14                                              |
| LA14   | Critério de bloqueio por informação sensível  | RF02, US16, CA21                                        |
| LA15   | Nova versão durante conversão existente       | Versionamento e rastreabilidade                         |

---

## 5. Exemplo de rastreabilidade ponta a ponta

### Exemplo 1 — Retomada de conversão

`RF12 → RN06/RN07 → US11 → UC02 → CA15/CA16`

Essa relação demonstra que:

* o RF12 define a necessidade funcional de preservar o progresso;
* as regras RN06 e RN07 definem as condições para preservação e retomada;
* a US11 representa o benefício para o usuário;
* o UC02 detalha o fluxo de interrupção e continuidade;
* os critérios CA15 e CA16 tornam o comportamento verificável.

---

### Exemplo 2 — Validação da conversão

`RF15 → RN03/RN04/RN10 → US14 → UC04 → CA11/CA19`

Nesse fluxo:

* o RF15 determina que processamento concluído e conversão validada são estados diferentes;
* as regras definem as condições para essa distinção;
* a US14 representa a necessidade do Líder Técnico;
* o UC04 detalha o processo de validação;
* os critérios de aceitação verificam que uma falha crítica impede a classificação como validada.

---

### Exemplo 3 — Proteção de informações sensíveis

`RF02 → RN02/RN09 → LA14 → US16 → UC01 → CA09/CA21`

Nesse caso:

* o sistema deve validar o conteúdo submetido;
* regras de segurança determinam o tratamento de segredos;
* ainda existe uma lacuna sobre quais tipos de informação devem bloquear o processamento;
* a necessidade é representada pela US16;
* o fluxo é detalhado no UC01;
* os critérios CA09 e CA21 estabelecem comportamentos verificáveis.

---

## 6. Benefícios da rastreabilidade

A matriz permite:

* identificar quais histórias representam cada requisito;
* localizar regras de negócio associadas;
* verificar quais requisitos possuem lacunas pendentes;
* relacionar casos de uso aos requisitos que detalham;
* localizar critérios de aceitação utilizados para validação;
* avaliar possíveis impactos quando um requisito for alterado;
* reduzir inconsistências entre os documentos.

---

## 7. Papel da Inteligência Artificial Generativa

A Inteligência Artificial Generativa foi utilizada como apoio na organização das relações entre os artefatos.

A IA ajudou a identificar possíveis associações entre requisitos, regras, histórias, casos de uso e critérios de aceitação.

Entretanto, as associações foram revisadas manualmente para evitar vínculos artificiais ou redundantes.

Também foi adotado o cuidado de não utilizar a IA para preencher automaticamente lacunas existentes.

Quando uma relação dependia de uma decisão ainda não definida, a lacuna foi mantida explicitamente na matriz.

---

## 8. Considerações finais

A rastreabilidade contribui para que os artefatos do RISC Convert sejam tratados como partes de uma mesma especificação, e não como documentos independentes.

Essa abordagem facilita validação, manutenção, análise de impacto e futura derivação de casos de teste.

A matriz também permite visualizar claramente quais pontos ainda dependem de validação dos stakeholders.
