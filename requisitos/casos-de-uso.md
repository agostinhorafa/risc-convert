# Casos de Uso — RISC Convert

## 1. Objetivo

Este documento apresenta os principais casos de uso do cenário fictício RISC Convert.

Os casos de uso foram selecionados apenas para os fluxos que exigem maior detalhamento de interação, regras, exceções e condições alternativas.

---

## 2. Atores

Os principais atores considerados são:

* Usuário da plataforma;
* Desenvolvedor;
* Líder Técnico;
* QA;
* Engenheiro de Plataforma;
* Especialista de Segurança;
* Serviço externo de Inteligência Artificial.

---

# UC01 — Submeter projeto para conversão

## Objetivo

Permitir que o usuário envie um projeto para análise e posterior conversão.

## Ator principal

Usuário da plataforma.

## Pré-condições

* O usuário possui um projeto disponível para submissão;
* A plataforma está disponível para receber novos projetos.

## Pós-condições

* O projeto é armazenado para análise;
* A validação inicial é executada;
* O usuário recebe o resultado da validação.

## Fluxo principal

1. O usuário acessa a opção de nova conversão.
2. O usuário informa ou envia o projeto.
3. O sistema recebe os arquivos.
4. O sistema valida o formato e a estrutura mínima.
5. O sistema verifica a existência de arquivos inválidos.
6. O sistema realiza verificação inicial de informações sensíveis.
7. O sistema registra a submissão.
8. O projeto é disponibilizado para a etapa de análise.
9. O usuário recebe confirmação de que a entrada foi aceita.

## Fluxos alternativos

### A1 — Formato inválido

1. O sistema identifica que o formato da entrada não é suportado.
2. A submissão é interrompida.
3. O usuário recebe uma mensagem informando o problema.
4. Nenhuma conversão é iniciada.

### A2 — Estrutura inválida

1. O sistema não identifica os elementos mínimos necessários para análise.
2. O sistema informa que o projeto não pode prosseguir.
3. O usuário poderá corrigir o projeto e realizar uma nova submissão.

### A3 — Informação sensível identificada

1. O sistema identifica uma possível credencial, token, chave ou segredo.
2. O envio para o serviço externo de IA é bloqueado.
3. O usuário é informado sobre a necessidade de tratamento da informação.
4. O processamento não prossegue até que a condição seja resolvida.

## Requisitos relacionados

RF01, RF02

## Regras relacionadas

RN01, RN02

## Histórias relacionadas

US01, US02, US16

---

# UC02 — Executar conversão do projeto

## Objetivo

Converter um projeto previamente validado utilizando Inteligência Artificial Generativa.

## Ator principal

Usuário da plataforma.

## Atores secundários

* Serviço externo de IA;
* Engenheiro de Plataforma.

## Pré-condições

* O projeto foi submetido;
* A entrada foi validada;
* Nenhum bloqueio crítico de segurança está ativo.

## Pós-condições

* A conversão é concluída;
* A conversão é concluída com ressalvas;
* Ou a conversão é registrada como falha.

## Fluxo principal

1. O usuário inicia a conversão.
2. O sistema cria uma execução com identificador único.
3. O sistema analisa a estrutura do projeto.
4. O sistema identifica arquivos, componentes e dependências.
5. O sistema registra dependências incompatíveis.
6. O sistema prepara o conteúdo necessário para conversão.
7. O sistema envia as informações permitidas ao serviço de IA.
8. O serviço externo retorna o conteúdo convertido.
9. O sistema armazena os artefatos produzidos.
10. O sistema registra a conclusão da etapa de conversão.
11. O processamento segue para validação.

## Fluxos alternativos

### A1 — Dependência incompatível

1. O sistema identifica uma dependência que não pode ser convertida automaticamente.
2. A dependência é registrada.
3. O processamento continua quando a incompatibilidade não for bloqueante.
4. O resultado poderá ser classificado como concluído com ressalvas.

### A2 — Falha temporária do serviço de IA

1. O serviço externo retorna erro ou indisponibilidade.
2. O sistema registra o evento.
3. A política de novas tentativas é aplicada.
4. Se uma tentativa posterior funcionar, o processamento continua.

### A3 — Falha persistente do serviço de IA

1. Todas as tentativas permitidas falham.
2. O estado já processado é preservado.
3. A conversão é interrompida.
4. O sistema registra o motivo da falha.
5. O usuário é informado.

### A4 — Falha interna durante o processamento

1. O sistema identifica um erro interno recuperável.
2. O estado da execução é preservado.
3. O processamento poderá ser retomado a partir do último checkpoint válido.

## Requisitos relacionados

RF03, RF04, RF05, RF06, RF08, RF12

## Regras relacionadas

RN01, RN05, RN06, RN07, RN08, RN11, RN12

## Histórias relacionadas

US03, US04, US05, US11, US18

---

# UC03 — Acompanhar conversão

## Objetivo

Permitir que o usuário acompanhe o andamento de uma conversão.

## Ator principal

Usuário da plataforma.

## Pré-condições

* Existe uma conversão registrada.

## Pós-condições

* O usuário visualiza o estado atual da execução.

## Fluxo principal

1. O usuário acessa uma conversão existente.
2. O sistema recupera o estado atual.
3. O sistema apresenta o status.
4. O sistema apresenta as etapas já executadas.
5. O sistema informa eventuais avisos ou erros disponíveis.
6. O usuário poderá consultar novamente até a finalização.

## Estados possíveis

* aguardando processamento;
* em análise;
* em conversão;
* em validação;
* concluída;
* concluída com ressalvas;
* falha.

## Fluxos alternativos

### A1 — Conversão interrompida

1. O sistema informa que a execução foi interrompida.
2. O motivo é apresentado, quando disponível.
3. O sistema informa se a conversão poderá ser retomada.

### A2 — Conversão concluída com ressalvas

1. O sistema apresenta o status correspondente.
2. O usuário visualiza os itens que necessitam intervenção manual.

## Requisitos relacionados

RF06, RF07, RF08, RF11, RF15

## Regras relacionadas

RN03, RN05, RN14

## Histórias relacionadas

US06, US07, US10, US15

---

# UC04 — Validar projeto convertido

## Objetivo

Executar verificações técnicas sobre o código convertido antes de classificá-lo como validado.

## Ator principal

Líder Técnico.

## Atores secundários

* Desenvolvedor;
* QA.

## Pré-condições

* A etapa de conversão foi concluída;
* Os artefatos convertidos estão disponíveis.

## Pós-condições

O resultado recebe uma das classificações:

* validada;
* concluída com ressalvas;
* falha de validação.

## Fluxo principal

1. O sistema inicia a validação do projeto convertido.
2. É executada a validação sintática.
3. O sistema executa o build ou compilação, quando aplicável.
4. Os testes automatizados disponíveis são executados.
5. Os resultados são registrados.
6. Dependências incompatíveis são verificadas.
7. O sistema apresenta o resultado das validações.
8. O responsável técnico revisa o resultado.
9. A conversão recebe o status apropriado.

## Fluxos alternativos

### A1 — Falha de build

1. O build falha.
2. O erro é registrado.
3. A conversão não pode ser classificada como validada.
4. O usuário recebe informações para investigação.

### A2 — Falha em teste obrigatório

1. Um teste obrigatório falha.
2. A falha é registrada.
3. A conversão não é classificada como validada.

### A3 — Projeto sem testes automatizados

1. O sistema identifica que não existem testes disponíveis.
2. A ausência é registrada.
3. O resultado indica limitação da validação funcional.
4. A decisão final depende de revisão técnica.

### A4 — Dependência não bloqueante

1. É identificada uma dependência incompatível que não impede o build.
2. O item é registrado.
3. A conversão poderá ser classificada como concluída com ressalvas.

## Requisitos relacionados

RF09, RF10, RF11, RF14, RF15

## Regras relacionadas

RN03, RN04, RN05, RN10, RN14

## Histórias relacionadas

US08, US09, US10, US13, US14, US15

## Lacunas relacionadas

LA08, LA09, LA11

---

# UC05 — Obter resultado da conversão

## Objetivo

Permitir que o usuário consulte o resultado final e obtenha os artefatos gerados.

## Ator principal

Usuário da plataforma.

## Pré-condições

* O processamento chegou a um estado final;
* Existem informações de resultado disponíveis.

## Pós-condições

* O usuário consulta o relatório;
* O usuário poderá baixar os artefatos disponíveis.

## Fluxo principal

1. O usuário acessa uma conversão finalizada.
2. O sistema apresenta o status final.
3. O sistema apresenta o relatório da execução.
4. O relatório informa o resultado do build.
5. O relatório informa o resultado dos testes.
6. O relatório apresenta dependências incompatíveis.
7. O relatório destaca itens que necessitam revisão.
8. O sistema disponibiliza os artefatos gerados.
9. O usuário realiza o download.

## Fluxos alternativos

### A1 — Conversão concluída com ressalvas

1. O sistema apresenta o status "Concluída com ressalvas".
2. Os problemas identificados são destacados.
3. Os artefatos são disponibilizados quando tecnicamente possível.
4. O usuário é informado de que existe necessidade de intervenção manual.

### A2 — Conversão com falha

1. O sistema apresenta o status de falha.
2. O relatório de erro fica disponível.
3. Artefatos parciais poderão ser disponibilizados quando aplicável.

## Requisitos relacionados

RF11, RF13, RF14, RF15

## Regras relacionadas

RN03, RN10, RN14, RN15

## Histórias relacionadas

US10, US12, US13, US14, US15

---

## 3. Casos de uso não formalizados

Alguns fluxos foram identificados, mas não foram transformados em casos de uso definitivos devido à existência de lacunas.

### Cancelar conversão

Não foi formalizado porque a política de cancelamento ainda depende de definição.

**Lacuna relacionada:** LA10

### Selecionar tecnologias de origem e destino

Ainda depende da definição das tecnologias oficialmente suportadas.

**Lacunas relacionadas:** LA01 e LA02

### Gerenciar retenção de artefatos

Não foi formalizado porque a política de retenção ainda não foi definida.

**Lacuna relacionada:** LA07

---

## 4. Papel da Inteligência Artificial Generativa

A IA Generativa foi utilizada para apoiar a identificação dos fluxos principais, alternativos e de exceção.

Algumas sugestões iniciais foram simplificadas para evitar casos de uso excessivamente detalhados ou redundantes em relação às histórias de usuário.

Também foram descartados casos de uso relacionados a funcionalidades ainda não definidas no cenário.

A decisão foi manter casos de uso apenas para processos em que o detalhamento das interações, regras e exceções agregava valor à especificação.

---

## 5. Considerações finais

Os casos de uso complementam as histórias de usuário ao detalhar fluxos críticos do RISC Convert.

Eles permitem representar cenários normais, alternativos e de falha, contribuindo para a identificação de lacunas e para a posterior criação de critérios de aceitação e casos de teste.
