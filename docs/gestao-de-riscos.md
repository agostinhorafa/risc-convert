# Gestão de Riscos — RISC Convert

## 1. Objetivo

Este documento apresenta o registro e a análise dos principais riscos identificados no projeto fictício RISC Convert.

O objetivo é apoiar a tomada de decisão da equipe do projeto por meio da identificação, avaliação e definição de estratégias de resposta para riscos técnicos, de qualidade, segurança, desempenho, operação e custo.

---

## 2. Metodologia de avaliação

Os riscos foram avaliados considerando probabilidade e impacto em uma escala de 1 a 5.

### Probabilidade

| Valor | Classificação |
|---|---|
| 1 | Muito baixa |
| 2 | Baixa |
| 3 | Média |
| 4 | Alta |
| 5 | Muito alta |

### Impacto

| Valor | Classificação |
|---|---|
| 1 | Muito baixo |
| 2 | Baixo |
| 3 | Médio |
| 4 | Alto |
| 5 | Muito alto |

### Cálculo da exposição

A exposição do risco é calculada por:

`Exposição = Probabilidade × Impacto`

A classificação utilizada foi:

| Exposição | Severidade |
|---|---|
| 1 a 5 | Baixa |
| 6 a 10 | Média |
| 11 a 15 | Alta |
| 16 a 25 | Crítica |

---

## 3. Registro de Riscos

| ID | Risco | Categoria | Probabilidade | Impacto | Exposição | Severidade | Estratégia |
|---|---|---|---:|---:|---:|---|---|
| R01 | Código convertido apresentar comportamento funcional diferente do sistema original | Qualidade | 4 | 5 | 20 | Crítica | Mitigar |
| R02 | Dependências ou componentes do sistema legado não possuírem conversão compatível | Técnico | 4 | 4 | 16 | Crítica | Mitigar |
| R03 | Projetos de grande porte apresentarem tempo de processamento acima do esperado | Desempenho | 3 | 4 | 12 | Alta | Mitigar |
| R04 | Serviço externo de IA ficar indisponível ou sofrer alteração de limites | Externo | 3 | 4 | 12 | Alta | Mitigar |
| R05 | Código submetido conter credenciais ou informações sensíveis | Segurança | 3 | 5 | 15 | Alta | Evitar / Mitigar |
| R06 | IA gerar código sintaticamente correto, porém com vulnerabilidades ou falhas de segurança | Segurança / Qualidade | 3 | 5 | 15 | Alta | Mitigar |
| R07 | Consumo do serviço de IA ultrapassar o orçamento previsto | Financeiro | 3 | 3 | 9 | Média | Mitigar |
| R08 | Falha durante uma conversão causar perda do progresso já realizado | Operacional | 3 | 4 | 12 | Alta | Mitigar |
| R09 | Falta de logs suficientes dificultar a investigação de erros | Operacional | 2 | 4 | 8 | Média | Mitigar |
| R10 | Usuário interpretar o código convertido como pronto para produção sem revisão técnica | Processo / Qualidade | 3 | 4 | 12 | Alta | Mitigar |

---

## 4. Detalhamento dos principais riscos

### R01 — Conversão funcionalmente incorreta

**Categoria:** Qualidade  
**Probabilidade:** Alta — 4  
**Impacto:** Muito alto — 5  
**Exposição:** 20  
**Severidade:** Crítica  
**Estratégia:** Mitigar

#### Descrição

O código produzido pela Inteligência Artificial Generativa pode compilar e executar normalmente, porém apresentar comportamento diferente da aplicação original ou implementar incorretamente regras de negócio.

#### Possíveis causas

- interpretação incorreta do código original pela IA;
- ausência de contexto suficiente durante a conversão;
- limitações do modelo generativo;
- regras de negócio implícitas ou pouco documentadas;
- dependências entre componentes não identificadas corretamente.

#### Possíveis impactos

- falhas funcionais;
- alteração do comportamento esperado da aplicação;
- retrabalho da equipe;
- aumento do prazo de entrega;
- redução da confiança dos usuários na plataforma.

#### Ações de resposta

- executar testes automatizados após a conversão;
- realizar validações de compilação e build;
- comparar comportamentos entre o sistema original e o convertido;
- registrar logs das etapas de conversão;
- exigir revisão técnica antes de considerar a conversão validada.

**Responsável:** Líder Técnico

---

### R02 — Dependências incompatíveis

**Categoria:** Técnico  
**Probabilidade:** Alta — 4  
**Impacto:** Alto — 4  
**Exposição:** 16  
**Severidade:** Crítica  
**Estratégia:** Mitigar

#### Descrição

Bibliotecas, frameworks, APIs ou componentes utilizados no sistema legado podem não possuir equivalentes diretos na tecnologia de destino.

#### Possíveis causas

- tecnologias obsoletas;
- bibliotecas descontinuadas;
- componentes proprietários;
- diferenças arquiteturais entre a tecnologia de origem e destino.

#### Possíveis impactos

- conversão incompleta;
- necessidade de intervenção manual;
- aumento do prazo;
- necessidade de substituição ou reimplementação de componentes.

#### Ações de resposta

- mapear dependências antes do início da conversão;
- manter uma lista de tecnologias suportadas;
- identificar previamente componentes incompatíveis;
- gerar alertas para itens que necessitem adaptação manual;
- documentar alternativas conhecidas para dependências não suportadas.

**Responsável:** Arquiteto de Software

---

### R03 — Tempo elevado de processamento

**Categoria:** Desempenho  
**Probabilidade:** Média — 3  
**Impacto:** Alto — 4  
**Exposição:** 12  
**Severidade:** Alta  
**Estratégia:** Mitigar

#### Descrição

Projetos com grande volume de arquivos ou alta complexidade podem apresentar tempo de processamento superior ao esperado.

#### Possíveis causas

- grande quantidade de arquivos;
- código com elevada complexidade;
- grande volume de chamadas ao modelo de IA;
- limitações de infraestrutura;
- necessidade de múltiplas tentativas de conversão.

#### Possíveis impactos

- aumento do tempo de entrega;
- piora da experiência do usuário;
- maior consumo de recursos computacionais;
- aumento dos custos de processamento.

#### Ações de resposta

- dividir projetos grandes em lotes;
- utilizar processamento assíncrono;
- implementar checkpoints;
- permitir retomada de conversões interrompidas;
- monitorar o tempo médio de processamento.

**Responsável:** Engenheiro de Plataforma

---

### R04 — Indisponibilidade do serviço de IA

**Categoria:** Externo  
**Probabilidade:** Média — 3  
**Impacto:** Alto — 4  
**Exposição:** 12  
**Severidade:** Alta  
**Estratégia:** Mitigar

#### Descrição

O provedor externo responsável pelo modelo de Inteligência Artificial pode apresentar indisponibilidade, lentidão ou alterações nos limites de utilização.

#### Possíveis causas

- indisponibilidade do fornecedor;
- limitação de requisições;
- alteração de políticas do serviço;
- mudança de modelo ou API;
- problemas de conectividade.

#### Possíveis impactos

- interrupção das conversões;
- aumento do tempo de processamento;
- indisponibilidade temporária da principal funcionalidade;
- atrasos no cronograma.

#### Ações de resposta

- implementar mecanismos de retry;
- utilizar filas de processamento;
- armazenar o estado atual das conversões;
- monitorar a disponibilidade do provedor;
- avaliar modelos ou provedores alternativos.

**Responsável:** Engenheiro de Plataforma

---

### R05 — Exposição de informações sensíveis

**Categoria:** Segurança  
**Probabilidade:** Média — 3  
**Impacto:** Muito alto — 5  
**Exposição:** 15  
**Severidade:** Alta  
**Estratégia:** Evitar / Mitigar

#### Descrição

O código-fonte submetido pelos usuários pode conter credenciais, tokens, chaves de API, URLs internas ou outras informações confidenciais.

#### Possíveis causas

- envio de arquivos contendo segredos;
- ausência de sanitização antes do processamento;
- armazenamento inadequado dos artefatos;
- compartilhamento de informações sensíveis com serviços externos.

#### Possíveis impactos

- vazamento de informações;
- comprometimento de credenciais;
- incidentes de segurança;
- impacto reputacional;
- necessidade de revogação de chaves e acessos.

#### Ações de resposta

- realizar análise automática para identificar possíveis segredos;
- impedir ou alertar sobre arquivos sensíveis, como `.env`;
- mascarar informações identificadas;
- definir política de retenção e exclusão dos arquivos submetidos;
- orientar usuários sobre práticas seguras antes do envio.

**Responsável:** Especialista de Segurança

---

## 5. Priorização

Os riscos R01 e R02 receberam prioridade máxima devido à combinação entre alta probabilidade e alto impacto.

O risco R01 foi considerado o mais relevante para o projeto, pois está diretamente relacionado à qualidade do principal resultado entregue pelo RISC Convert.

Mesmo que a plataforma conclua o processamento sem erros técnicos, um código convertido que apresente comportamento diferente da aplicação original representa uma falha crítica no objetivo da solução.

Por esse motivo, foi definida uma estratégia específica de resposta baseada em validação automatizada, testes e revisão técnica humana.

---

## 6. Monitoramento dos riscos

Os riscos devem ser revisados periodicamente durante a evolução do projeto.

O acompanhamento deve considerar:

- alteração da probabilidade ou impacto;
- ocorrência de novos riscos;
- eficácia das ações de mitigação;
- surgimento de novos componentes ou dependências;
- alterações nos serviços externos utilizados;
- aumento do volume ou complexidade dos projetos processados;
- ocorrências identificadas durante testes e validações.

A matriz de riscos deve ser atualizada sempre que mudanças relevantes ocorrerem no projeto.

---

## 7. Considerações finais

A gestão de riscos do RISC Convert busca reduzir incertezas relacionadas principalmente ao uso de Inteligência Artificial Generativa na conversão automatizada de software.

Embora a IA permita acelerar tarefas de análise e transformação de código, seus resultados não devem ser considerados automaticamente corretos.

A combinação entre automação, monitoramento, testes e validação humana é fundamental para garantir maior confiabilidade no processo de conversão.
