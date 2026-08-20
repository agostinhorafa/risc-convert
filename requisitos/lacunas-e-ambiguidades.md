# Lacunas e Ambiguidades — RISC Convert

## 1. Objetivo

Este documento registra lacunas, ambiguidades, decisões pendentes e pontos que ainda necessitam de validação no cenário fictício RISC Convert.

O objetivo é evitar que informações não definidas sejam tratadas como requisitos ou regras de negócio definitivas.

Durante a análise, a Inteligência Artificial Generativa foi utilizada para apoiar a identificação desses pontos, mas nenhuma lacuna foi preenchida automaticamente sem respaldo no cenário.

---

## 2. Lacunas identificadas

### LA01 — Tecnologias de origem suportadas

**Descrição:**
Ainda não foi definida a lista de linguagens, frameworks e tecnologias legadas que poderão ser submetidas à plataforma.

**Impacto:**
Sem essa definição, não é possível determinar com precisão o escopo de conversão suportado.

**Pergunta para validação:**
Quais linguagens e frameworks de origem devem ser oficialmente suportados pelo RISC Convert?

**Prioridade:** Alta

**Status:** Pendente de validação

---

### LA02 — Tecnologias de destino suportadas

**Descrição:**
Não foi definida a lista de tecnologias para as quais os projetos poderão ser convertidos.

**Impacto:**
A ausência dessa informação impede a definição completa das regras de compatibilidade e validação.

**Pergunta para validação:**
Quais tecnologias de destino deverão ser disponibilizadas aos usuários?

**Prioridade:** Alta

**Status:** Pendente de validação

---

### LA03 — Tamanho máximo do projeto

**Descrição:**
Não há definição sobre o tamanho máximo permitido para projetos submetidos.

**Impacto:**
Projetos muito grandes podem afetar desempenho, custo, tempo de processamento e capacidade de infraestrutura.

**Pergunta para validação:**
Qual deve ser o limite máximo de tamanho para um projeto submetido?

**Prioridade:** Alta

**Status:** Pendente de validação

---

### LA04 — Tempo máximo aceitável de processamento

**Descrição:**
Não foi estabelecido um tempo máximo esperado para conclusão de uma conversão.

**Impacto:**
Sem um valor de referência, não é possível definir SLA ou avaliar objetivamente quando uma conversão está lenta.

**Pergunta para validação:**
Qual o tempo aceitável de processamento para projetos pequenos, médios e grandes?

**Prioridade:** Média

**Status:** Pendente de validação

---

### LA05 — Quantidade de conversões simultâneas

**Descrição:**
Não há informação sobre quantas conversões a plataforma deverá processar ao mesmo tempo.

**Impacto:**
Essa definição influencia diretamente requisitos de infraestrutura, escalabilidade e desempenho.

**Pergunta para validação:**
Qual o volume esperado de conversões simultâneas?

**Prioridade:** Média

**Status:** Pendente de validação

---

### LA06 — Número máximo de tentativas com o serviço de IA

**Descrição:**
Foi identificada a necessidade de novas tentativas em caso de falha temporária do serviço externo, porém o número máximo não foi definido.

**Impacto:**
Tentativas excessivas podem aumentar custo e tempo de processamento; tentativas insuficientes podem encerrar conversões recuperáveis.

**Pergunta para validação:**
Quantas tentativas devem ser realizadas antes de considerar a comunicação com o serviço de IA como falha definitiva?

**Prioridade:** Média

**Status:** Pendente de validação

---

### LA07 — Política de retenção dos arquivos

**Descrição:**
Não foram definidos os períodos de armazenamento do código submetido, dos artefatos convertidos e dos logs.

**Impacto:**
A ausência de uma política pode gerar riscos de segurança, privacidade, custo de armazenamento e rastreabilidade.

**Perguntas para validação:**

* Por quanto tempo o projeto original deve permanecer armazenado?
* Por quanto tempo os artefatos convertidos devem ficar disponíveis?
* Qual deve ser o período de retenção dos logs?

**Prioridade:** Alta

**Status:** Pendente de validação

---

### LA08 — Critério definitivo para uma conversão validada

**Descrição:**
O cenário diferencia processamento concluído de conversão validada, porém ainda não há definição completa dos critérios obrigatórios para validação.

**Impacto:**
Sem critérios claros, diferentes usuários ou equipes podem interpretar o resultado de forma distinta.

**Pergunta para validação:**
Quais condições devem ser obrigatoriamente atendidas para que uma conversão receba status de validada?

**Prioridade:** Crítica

**Status:** Pendente de validação

---

### LA09 — Tratamento de testes inexistentes

**Descrição:**
Não foi definido como a plataforma deverá avaliar uma conversão quando o projeto de origem não possuir testes automatizados.

**Impacto:**
A ausência de testes reduz a capacidade de verificar regressões e equivalência funcional.

**Pergunta para validação:**
A plataforma deverá gerar testes, exigir testes previamente existentes ou apenas informar que a validação funcional ficou limitada?

**Prioridade:** Alta

**Status:** Pendente de validação

---

### LA10 — Cancelamento de conversão

**Descrição:**
Não está definido se o usuário poderá cancelar uma conversão em andamento.

**Impacto:**
Sem uma regra clara, o comportamento esperado da plataforma em processamentos longos permanece ambíguo.

**Perguntas para validação:**

* O cancelamento será permitido?
* Em quais etapas?
* Os artefatos já gerados serão preservados?
* O cancelamento poderá ser revertido?

**Prioridade:** Média

**Status:** Pendente de validação

---

### LA11 — Tratamento de conversões parcialmente concluídas

**Descrição:**
Ainda não está totalmente definido quando uma conversão deve ser classificada como falha ou concluída com ressalvas.

**Impacto:**
A ausência dessa regra pode gerar inconsistência na apresentação do resultado ao usuário.

**Pergunta para validação:**
Quais tipos de falha permitem concluir a conversão com ressalvas e quais devem impedir sua conclusão?

**Prioridade:** Alta

**Status:** Pendente de validação

---

### LA12 — Critério de incompatibilidade de dependências

**Descrição:**
Não foi definido o critério utilizado para classificar uma dependência como incompatível.

**Impacto:**
A mesma dependência pode ser interpretada de forma diferente por diferentes versões do mecanismo de análise.

**Pergunta para validação:**
Uma dependência é considerada incompatível somente quando não existe equivalente automático ou também quando exige adaptação manual?

**Prioridade:** Média

**Status:** Pendente de validação

---

### LA13 — Responsabilidade sobre a revisão final

**Descrição:**
O cenário estabelece que o resultado deve passar por revisão humana, porém não define formalmente quem deve executar essa revisão.

**Impacto:**
A ausência de definição pode gerar dúvida sobre responsabilidade e aprovação final.

**Pergunta para validação:**
Qual perfil será responsável pela revisão e aprovação técnica da conversão?

**Prioridade:** Alta

**Status:** Pendente de validação

---

### LA14 — Critério de segurança para envio ao serviço externo

**Descrição:**
Foi definida a necessidade de detectar informações sensíveis, mas não foi estabelecido quais tipos de informação devem bloquear automaticamente o processamento.

**Impacto:**
A falta de critério pode gerar tanto bloqueios excessivos quanto exposição indevida de informações.

**Pergunta para validação:**
Quais tipos de segredos ou informações devem impedir obrigatoriamente o envio do conteúdo ao serviço externo de IA?

**Prioridade:** Crítica

**Status:** Pendente de validação

---

### LA15 — Comportamento em alteração do projeto durante uma conversão

**Descrição:**
Não foi definido o que acontece caso uma nova versão do projeto seja enviada enquanto uma conversão anterior ainda está em andamento.

**Impacto:**
Pode haver dúvida sobre versionamento, rastreabilidade e associação dos resultados.

**Pergunta para validação:**
Uma nova versão deve iniciar uma nova conversão independente ou substituir a execução anterior?

**Prioridade:** Média

**Status:** Pendente de validação

---

## 3. Ambiguidades identificadas

### AM01 — “Conversão concluída”

A expressão “conversão concluída” pode ser interpretada como:

* processamento técnico encerrado;
* build executado com sucesso;
* testes aprovados;
* código validado;
* código pronto para produção.

Para evitar ambiguidade, o projeto utiliza estados distintos, como:

* concluída;
* concluída com ressalvas;
* validada.

---

### AM02 — “Projeto compatível”

O termo “compatível” pode significar:

* tecnologia reconhecida pela plataforma;
* tecnologia suportada para análise;
* tecnologia suportada para conversão automática;
* tecnologia parcialmente suportada.

É necessário estabelecer uma classificação formal de compatibilidade.

---

### AM03 — “Falha crítica”

O termo precisa ser definido de forma objetiva.

Uma falha pode ser considerada crítica quando:

* impede o build;
* causa falha em testes obrigatórios;
* compromete segurança;
* impede execução da aplicação;
* altera uma regra de negócio essencial.

A lista definitiva ainda precisa ser validada.

---

### AM04 — “Revisão técnica”

Ainda não está definido o nível de revisão necessário.

A expressão pode envolver:

* inspeção manual do código;
* revisão de logs;
* revisão por pares;
* execução adicional de testes;
* aprovação formal por um responsável técnico.

Esse ponto deverá ser esclarecido.

---

### AM05 — “Informação sensível”

O termo pode incluir diferentes tipos de dado, como:

* senhas;
* tokens;
* chaves de API;
* certificados;
* endpoints internos;
* dados pessoais;
* informações comerciais.

É necessário definir quais categorias terão tratamento obrigatório.

---

## 4. Sugestões da IA não transformadas em requisitos

Durante a análise, a Inteligência Artificial Generativa sugeriu algumas definições que poderiam parecer plausíveis, mas não estavam sustentadas pelo cenário.

Exemplos:

* limite máximo de 100 MB por projeto;
* processamento concluído em até 10 minutos;
* três tentativas automáticas em caso de falha;
* retenção dos arquivos por 30 dias;
* disponibilidade mensal de 99,9%;
* suporte inicial obrigatório a determinadas linguagens;
* exclusão automática dos arquivos após um período específico.

Essas sugestões não foram incorporadas como requisitos definitivos.

Elas foram tratadas como exemplos de pontos que precisam de validação dos stakeholders.

---

## 5. Critério adotado para tratamento das lacunas

Foi adotada a seguinte regra:

> Se uma informação necessária não estiver definida no cenário, ela não deve ser inventada ou tratada como decisão já tomada.

Nesses casos, o ponto deve ser registrado como:

* lacuna;
* pergunta de esclarecimento;
* hipótese;
* proposta a validar.

Essa abordagem reduz o risco de transformar uma inferência da IA em requisito oficial.

---

## 6. Papel da Inteligência Artificial Generativa

A IA Generativa foi utilizada como apoio para questionar os requisitos existentes e identificar informações ausentes.

Ela foi especialmente útil para:

* levantar cenários alternativos;
* identificar termos subjetivos;
* encontrar regras sem critérios objetivos;
* sugerir perguntas de esclarecimento;
* apontar dependências entre requisitos;
* identificar possíveis decisões ainda não tomadas.

As sugestões foram revisadas antes de serem registradas.

---

## 7. Considerações finais

O registro separado de lacunas e ambiguidades evita que decisões pendentes fiquem escondidas dentro dos requisitos.

Esse cuidado é especialmente importante durante o uso de Inteligência Artificial Generativa, pois modelos generativos podem preencher informações ausentes com valores plausíveis.

No RISC Convert, informações não confirmadas são mantidas explicitamente como pendentes de validação.
