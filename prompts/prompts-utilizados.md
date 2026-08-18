# Prompts utilizados — RISC Convert

## 1. Objetivo

Este documento registra exemplos de prompts utilizados durante a elaboração dos artefatos de gerenciamento de riscos e comunicação do projeto fictício RISC Convert.

Os prompts foram utilizados como apoio para brainstorming, estruturação das informações, análise de riscos e elaboração da documentação.

As respostas produzidas pela Inteligência Artificial Generativa foram revisadas e adaptadas antes de serem incorporadas aos documentos finais.

---

## 2. Contextualização do projeto

### Prompt

> Considere um projeto fictício chamado RISC Convert, uma plataforma web destinada à modernização de aplicações legadas com apoio de Inteligência Artificial Generativa.
>
> A plataforma recebe o código-fonte de uma aplicação, analisa sua estrutura e dependências, utiliza um modelo de IA Generativa para apoiar a conversão para uma tecnologia de destino e realiza validações antes de disponibilizar os artefatos gerados para revisão e download.
>
> Considere uma arquitetura composta por frontend React, backend Python com FastAPI, banco PostgreSQL, processamento assíncrono e integração com um serviço externo de IA.
>
> Estruture uma descrição objetiva do cenário, considerando que será utilizado em uma atividade acadêmica de gerenciamento de projetos de software.

### Utilização da resposta

A resposta foi utilizada como apoio para estruturar a descrição inicial do projeto e seu fluxo de funcionamento.

---

## 3. Identificação inicial dos riscos

### Prompt

> Considerando o cenário do RISC Convert, identifique possíveis riscos do projeto relacionados às seguintes categorias:
>
> * qualidade;
> * segurança;
> * tecnologia;
> * desempenho;
> * infraestrutura;
> * serviços externos;
> * operação;
> * custos;
> * processos.
>
> Para cada risco, apresente uma descrição breve da causa e do possível impacto.
>
> Evite riscos genéricos e priorize situações diretamente relacionadas a uma plataforma de conversão de código baseada em Inteligência Artificial Generativa.

### Utilização da resposta

O resultado foi utilizado como brainstorming inicial.

Os riscos sugeridos foram analisados, agrupados e revisados antes da elaboração do Risk Register.

---

## 4. Análise de probabilidade e impacto

### Prompt

> Para os riscos identificados no projeto RISC Convert, proponha uma avaliação inicial de probabilidade e impacto utilizando uma escala de 1 a 5.
>
> Considere:
>
> 1 = Muito baixo
> 2 = Baixo
> 3 = Médio
> 4 = Alto
> 5 = Muito alto
>
> Calcule a exposição utilizando:
>
> Exposição = Probabilidade × Impacto
>
> Classifique os resultados da seguinte forma:
>
> * 1 a 5: Baixo;
> * 6 a 10: Médio;
> * 11 a 15: Alto;
> * 16 a 25: Crítico.
>
> Apresente o resultado em formato de Risk Register.
>
> Trate os valores como sugestões iniciais que deverão passar por validação humana.

### Utilização da resposta

A IA auxiliou na construção de uma primeira classificação dos riscos.

Os valores foram posteriormente revisados de acordo com o cenário definido para o projeto.

---

## 5. Priorização dos riscos

### Prompt

> Analise o Risk Register do RISC Convert e indique quais riscos deveriam receber maior prioridade.
>
> Considere não apenas o valor numérico da exposição, mas também a relação de cada risco com o objetivo principal do produto.
>
> Justifique qual risco deveria ser considerado prioritário para o projeto.

### Utilização da resposta

A análise contribuiu para a seleção do risco R01 — Conversão funcionalmente incorreta — como risco prioritário.

A decisão final considerou que esse risco compromete diretamente o principal valor entregue pela plataforma.

---

## 6. Estratégia de resposta para o risco prioritário

### Prompt

> Considere o seguinte risco do projeto RISC Convert:
>
> R01 — O código convertido pela Inteligência Artificial pode compilar e executar, mas apresentar comportamento funcional diferente da aplicação original.
>
> Desenvolva uma estratégia de mitigação em múltiplas camadas.
>
> Considere:
>
> * validação sintática;
> * build;
> * testes automatizados;
> * testes de regressão;
> * comparação funcional;
> * análise de logs;
> * revisão humana.
>
> Explique a finalidade de cada camada e proponha critérios para determinar quando uma conversão pode ser considerada tecnicamente válida.

### Utilização da resposta

A resposta apoiou a construção do plano de resposta detalhado para o principal risco do projeto.

---

## 7. Estratégias para os demais riscos

### Prompt

> Para cada risco do Risk Register do RISC Convert, indique uma estratégia de resposta adequada entre:
>
> * evitar;
> * mitigar;
> * transferir;
> * aceitar.
>
> Para cada risco, sugira ações práticas que possam ser adotadas pela equipe.
>
> Considere limitações realistas de prazo, equipe e orçamento.

### Utilização da resposta

As sugestões foram utilizadas como ponto de partida para as ações registradas no plano de resposta aos riscos.

---

## 8. Plano de comunicação

### Prompt

> Crie um plano de comunicação para o projeto RISC Convert.
>
> Considere os seguintes stakeholders:
>
> * Gerente de Projeto;
> * Product Owner;
> * Líder Técnico;
> * Desenvolvedores;
> * QA;
> * Engenheiro de Plataforma;
> * Especialista de Segurança;
> * Sponsor;
> * usuários piloto.
>
> Para cada stakeholder, indique:
>
> * informação que deve ser comunicada;
> * frequência;
> * canal;
> * responsável pela comunicação.
>
> Considere também como riscos críticos e incidentes devem ser comunicados.

### Utilização da resposta

A resposta foi utilizada para estruturar a matriz de comunicação e os fluxos de comunicação de riscos e incidentes.

---

## 9. Comunicação de um risco crítico

### Prompt

> Elabore um exemplo de comunicação sobre um risco crítico do projeto RISC Convert.
>
> Utilize o risco R01 — Conversão funcionalmente incorreta.
>
> A comunicação deve conter:
>
> * identificação do risco;
> * severidade;
> * situação;
> * impacto potencial;
> * estratégia de resposta;
> * responsável;
> * próxima atualização.
>
> Use uma linguagem objetiva e adequada ao gerenciamento de projetos.

### Utilização da resposta

A resposta auxiliou na criação do modelo de comunicação de risco crítico incluído no plano de comunicação.

---

## 10. Comunicação executiva

### Prompt

> Considere que o Gerente de Projeto precisa comunicar ao Sponsor a situação atual do RISC Convert.
>
> Transforme informações técnicas sobre erros de conversão, incompatibilidade de dependências e indisponibilidade do serviço de IA em um resumo executivo.
>
> Priorize:
>
> * impacto no projeto;
> * prazo;
> * qualidade;
> * custo;
> * decisões necessárias.
>
> Evite detalhes técnicos que não sejam necessários para a tomada de decisão.

### Utilização da resposta

O prompt foi utilizado para avaliar a capacidade da IA de adaptar uma mesma informação para diferentes públicos.

---

## 11. Identificação de limitações da própria IA

### Prompt

> Analise criticamente o uso de Inteligência Artificial Generativa no gerenciamento de riscos de um projeto de software.
>
> Identifique limitações e cuidados relacionados a:
>
> * respostas genéricas;
> * alucinação;
> * classificação de probabilidade e impacto sem dados históricos;
> * confidencialidade;
> * dependência da qualidade do contexto;
> * necessidade de revisão humana.
>
> Diferencie atividades em que a IA pode apoiar daquelas em que a decisão deve permanecer humana.

### Utilização da resposta

A análise foi utilizada como apoio para documentar limitações e cuidados percebidos durante a realização da atividade.

---

## 12. Revisão crítica dos resultados

### Prompt

> Revise os riscos e estratégias definidos para o RISC Convert.
>
> Identifique:
>
> * riscos excessivamente genéricos;
> * riscos redundantes;
> * estratégias pouco realistas;
> * classificações de probabilidade ou impacto que precisem de maior justificativa;
> * ações que dependam de recursos não previstos no cenário.
>
> Não altere automaticamente o conteúdo. Apenas apresente pontos que devem ser revisados por uma pessoa responsável pelo projeto.

### Utilização da resposta

Esse tipo de prompt foi utilizado para apoiar uma revisão crítica dos artefatos, sem delegar à IA a decisão final sobre quais alterações deveriam ser realizadas.

---

## 13. Cuidados adotados durante os prompts

Durante a elaboração da atividade, os prompts foram construídos utilizando apenas informações do cenário fictício.

Não foram compartilhados:

* nomes de clientes reais;
* nomes de organizações;
* credenciais;
* tokens;
* chaves de API;
* código-fonte proprietário;
* dados pessoais;
* métricas internas;
* informações comerciais confidenciais.

Sempre que necessário, informações foram substituídas por exemplos ou dados fictícios.

---

## 14. Considerações finais

Os prompts demonstram que a Inteligência Artificial Generativa foi utilizada principalmente como ferramenta de apoio ao raciocínio, brainstorming, organização e documentação.

As respostas da IA não foram consideradas automaticamente corretas.

O processo adotado foi:

`Contextualização → Prompt → Resposta da IA → Análise humana → Ajuste → Uso no artefato`

Dessa forma, a IA apoiou a realização da atividade sem substituir a responsabilidade humana pela avaliação dos riscos, priorização e tomada de decisão.
