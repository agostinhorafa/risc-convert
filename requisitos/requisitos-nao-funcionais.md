# Requisitos Não Funcionais — RISC Convert

## 1. Objetivo

Este documento apresenta os requisitos não funcionais do cenário fictício RISC Convert.

Os requisitos não funcionais definem atributos de qualidade, restrições e características esperadas da solução relacionadas principalmente a desempenho, segurança, disponibilidade, rastreabilidade, confiabilidade e usabilidade.

Sempre que possível, os requisitos foram descritos de forma verificável, evitando expressões subjetivas como “rápido”, “seguro” ou “fácil de usar”.

---

## 2. Requisitos Não Funcionais

### RNF01 — Segurança no armazenamento de credenciais

Credenciais, tokens, chaves de API e outros segredos utilizados pela plataforma não devem ser armazenados diretamente no código-fonte da aplicação.

Essas informações devem ser armazenadas por meio de mecanismos apropriados de configuração segura, como variáveis de ambiente ou serviços equivalentes de gerenciamento de segredos.

---

### RNF02 — Proteção de dados durante a transmissão

As comunicações entre o usuário e a plataforma, assim como entre a plataforma e serviços externos, devem utilizar canais de comunicação criptografados.

O sistema deve utilizar HTTPS/TLS nas comunicações realizadas por rede.

---

### RNF03 — Detecção de informações sensíveis

Antes do envio de conteúdo para serviços externos de Inteligência Artificial, a plataforma deve executar uma etapa de verificação destinada a identificar possíveis informações sensíveis no código-fonte.

Quando forem identificadas credenciais, tokens, chaves ou informações similares, o sistema deve bloquear o processamento ou solicitar tratamento prévio antes de prosseguir.

---

### RNF04 — Rastreabilidade das conversões

Cada execução de conversão deve possuir um identificador único.

Esse identificador deve permitir relacionar:

* projeto submetido;
* data e horário da execução;
* etapas realizadas;
* logs;
* resultado das validações;
* artefatos produzidos;
* situação final da conversão.

---

### RNF05 — Integridade dos logs

Os logs da conversão devem preservar a ordem cronológica dos eventos e permitir a identificação da etapa em que cada evento ocorreu.

Os registros não devem conter credenciais ou segredos em texto aberto.

---

### RNF06 — Recuperação após interrupção

Em caso de interrupção recuperável do processamento, o sistema deve preservar o estado das etapas já concluídas.

Sempre que tecnicamente possível, uma nova execução deve continuar a partir do último checkpoint válido, evitando o reprocessamento completo do projeto.

---

### RNF07 — Isolamento entre projetos

Os arquivos, logs e resultados associados a uma conversão não devem ser misturados com os dados pertencentes a outra execução.

Cada projeto deve possuir contexto de processamento isolado.

---

### RNF08 — Tratamento de indisponibilidade externa

Quando o serviço externo de Inteligência Artificial estiver temporariamente indisponível, a plataforma deve tratar a falha sem perder o estado atual da conversão.

A indisponibilidade deve ser registrada em log e comunicada ao usuário por meio de um status apropriado.

---

### RNF09 — Controle de tentativas

As novas tentativas de comunicação com serviços externos devem possuir quantidade limitada e intervalo controlado.

O sistema não deve executar tentativas indefinidamente em caso de falha persistente.

O limite exato de tentativas deverá ser definido como parâmetro de configuração do ambiente.

---

### RNF10 — Monitoramento do tempo de processamento

A plataforma deve registrar o tempo total de processamento de cada conversão e, quando possível, o tempo gasto em cada etapa.

Esses dados devem permitir identificar conversões com duração anormalmente elevada.

---

### RNF11 — Capacidade de processamento assíncrono

A execução de uma conversão não deve depender da permanência do usuário na página durante todo o processamento.

O processamento deve ocorrer de forma assíncrona, permitindo que o usuário consulte posteriormente o status da execução.

---

### RNF12 — Disponibilidade do histórico

As informações referentes às conversões realizadas devem permanecer disponíveis durante o período de retenção definido para o projeto.

O período exato de retenção ainda deverá ser validado antes de ser considerado uma regra definitiva.

---

### RNF13 — Clareza dos estados de processamento

Os estados apresentados ao usuário devem utilizar nomenclaturas distintas e compreensíveis.

O sistema deve diferenciar, no mínimo:

* aguardando;
* processando;
* validando;
* concluído;
* concluído com ressalvas;
* falha.

Estados distintos não devem utilizar a mesma indicação visual ou textual.

---

### RNF14 — Mensagens de erro compreensíveis

As mensagens apresentadas ao usuário devem informar o que ocorreu e, quando possível, indicar a próxima ação recomendada.

Detalhes exclusivamente técnicos, como stack traces completos, não devem ser exibidos como mensagem principal ao usuário final.

---

### RNF15 — Proteção dos artefatos temporários

Os arquivos temporários gerados durante a análise e conversão devem ser armazenados de forma controlada e removidos de acordo com a política de retenção definida para a plataforma.

O prazo exato de exclusão deverá ser validado com os responsáveis pelo projeto.

---

### RNF16 — Revisão humana

A interface e a documentação da plataforma devem deixar explícito que os artefatos gerados por Inteligência Artificial necessitam de revisão técnica antes de serem utilizados em ambiente de produção.

A plataforma não deve apresentar automaticamente uma conversão concluída como equivalente a código aprovado para produção.

---

## 3. Requisitos não funcionais ainda pendentes de definição

Alguns requisitos não funcionais foram identificados durante a análise, mas não possuem informações suficientes para serem definidos de forma mensurável.

Eles serão tratados como lacunas até que existam informações adicionais.

### Desempenho

Ainda não foi definido:

* tempo máximo aceitável para conversões;
* tempo máximo de resposta da interface;
* quantidade de conversões simultâneas suportadas;
* tamanho máximo dos projetos submetidos.

### Disponibilidade

Ainda não foi definido:

* percentual mínimo de disponibilidade mensal;
* tempo máximo aceitável de indisponibilidade;
* objetivos de recuperação do serviço.

### Retenção de dados

Ainda não foi definido:

* período de retenção dos projetos submetidos;
* período de retenção dos artefatos convertidos;
* período de retenção dos logs.

### Escalabilidade

Ainda não foi definido:

* volume esperado de usuários;
* quantidade máxima de projetos processados simultaneamente;
* crescimento esperado da utilização da plataforma.

Esses valores não devem ser inventados ou tratados como requisitos definitivos sem validação.

---

## 4. Observações sobre o uso da IA

Durante a elaboração dos requisitos não funcionais, a Inteligência Artificial Generativa foi utilizada como apoio para identificar categorias de qualidade relevantes para a solução.

Algumas sugestões iniciais da IA utilizavam expressões genéricas, como:

* “o sistema deve possuir alta disponibilidade”;
* “o sistema deve responder rapidamente”;
* “o sistema deve ser escalável”;
* “o sistema deve possuir boa usabilidade”.

Essas sugestões não foram utilizadas diretamente por não apresentarem critérios verificáveis.

Quando não havia dados suficientes para definir valores mensuráveis, os pontos foram mantidos como lacunas a serem validadas posteriormente.

---

## 5. Considerações finais

Os requisitos não funcionais do RISC Convert complementam os requisitos funcionais ao estabelecer atributos de qualidade e restrições importantes para uma plataforma que processa código-fonte com apoio de Inteligência Artificial Generativa.

A definição dos requisitos buscou evitar suposições não sustentadas pelo cenário.

Informações que ainda dependem de decisão dos stakeholders foram mantidas explicitamente como pendências, em vez de serem transformadas em requisitos definitivos.
