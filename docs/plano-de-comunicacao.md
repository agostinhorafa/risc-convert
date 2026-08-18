# Plano de Comunicação — RISC Convert

## 1. Objetivo

Este documento apresenta o plano de comunicação do projeto fictício RISC Convert.

O objetivo é definir quais informações devem ser compartilhadas, com quais públicos, em que frequência, por quais canais e com quais responsáveis, garantindo transparência sobre o andamento do projeto, riscos, impedimentos e decisões relevantes.

---

## 2. Princípios de comunicação

A comunicação do projeto deverá seguir os seguintes princípios:

- clareza;
- objetividade;
- rastreabilidade;
- adequação da linguagem ao público;
- comunicação antecipada de riscos e impedimentos;
- transparência sobre limitações da Inteligência Artificial;
- registro das decisões relevantes.

---

## 3. Stakeholders do projeto

Os principais stakeholders considerados no cenário são:

- Gerente de Projeto;
- Product Owner;
- Líder Técnico;
- Equipe de Desenvolvimento;
- QA;
- Engenheiro de Plataforma;
- Especialista de Segurança;
- Sponsor;
- Usuários piloto.

---

## 4. Matriz de comunicação

| Stakeholder | Informação comunicada | Frequência | Canal | Responsável |
|---|---|---|---|---|
| Gerente de Projeto | Status geral, cronograma, riscos, impedimentos e decisões | Semanal | Reunião de acompanhamento + relatório | Equipe do projeto |
| Product Owner | Evolução das funcionalidades, riscos, impactos e prioridades | Semanal | Reunião de acompanhamento | Gerente de Projeto |
| Líder Técnico | Falhas de conversão, riscos técnicos, dependências e ações corretivas | Contínua | Reuniões técnicas + ferramenta de acompanhamento | Equipe técnica |
| Desenvolvedores | Requisitos, impedimentos, problemas técnicos e prioridades | Diária | Daily / ferramenta de gestão | Líder Técnico |
| QA | Funcionalidades disponíveis para validação, riscos e resultados dos testes | Contínua | Ferramenta de gestão + reuniões técnicas | Líder Técnico |
| Engenheiro de Plataforma | Falhas de infraestrutura, desempenho, processamento e disponibilidade | Contínua | Alertas + ferramenta de acompanhamento | Gerente de Projeto |
| Especialista de Segurança | Riscos de segurança, exposição de dados e incidentes | Sob demanda | Alerta + relatório técnico | Líder Técnico |
| Sponsor | Evolução geral, riscos críticos, prazo e decisões necessárias | Mensal | Relatório executivo | Gerente de Projeto |
| Usuários piloto | Resultado das conversões, limitações conhecidas e orientações de uso | Por versão | E-mail + documentação | Product Owner |

---

## 5. Comunicação de riscos

Os riscos classificados como críticos ou altos deverão ser comunicados assim que identificados ou quando houver alteração relevante em sua probabilidade ou impacto.

A comunicação deverá conter, sempre que possível:

- identificação do risco;
- descrição;
- probabilidade;
- impacto;
- exposição;
- possível efeito sobre o projeto;
- estratégia de resposta;
- responsável;
- prazo para ação.

---

## 6. Comunicação de incidentes críticos

Quando ocorrer um incidente que possa comprometer a continuidade da conversão, a segurança das informações ou a qualidade do código gerado, deverá ser realizada uma comunicação imediata.

### Fluxo de comunicação

1. Identificação do incidente;
2. Registro na ferramenta de acompanhamento;
3. Comunicação ao Líder Técnico e ao Gerente de Projeto;
4. Avaliação inicial do impacto;
5. Acionamento de especialistas responsáveis;
6. Definição da ação de contenção;
7. Comunicação aos stakeholders afetados;
8. Atualização periódica até a resolução;
9. Registro da causa e das ações tomadas.

---

## 7. Comunicação com o Sponsor

O Sponsor receberá um resumo executivo mensal contendo:

- evolução do projeto;
- principais entregas realizadas;
- situação do cronograma;
- riscos críticos;
- impedimentos relevantes;
- decisões pendentes;
- consumo de recursos;
- ações planejadas para o próximo período.

A comunicação deverá evitar excesso de detalhes técnicos e priorizar informações relacionadas a impacto, prazo, custo, qualidade e tomada de decisão.

---

## 8. Comunicação com a equipe técnica

A equipe técnica deverá receber informações mais detalhadas sobre:

- falhas na conversão;
- incompatibilidade de dependências;
- erros de build;
- falhas nos testes;
- vulnerabilidades detectadas;
- indisponibilidade do serviço de IA;
- problemas de desempenho;
- necessidade de intervenção manual.

Sempre que possível, as ocorrências deverão conter evidências, logs e informações suficientes para facilitar a investigação.

---

## 9. Comunicação com usuários piloto

Os usuários piloto deverão receber informações claras sobre o funcionamento e as limitações da solução.

A comunicação deverá deixar explícito que:

- o código é gerado com apoio de Inteligência Artificial;
- a conclusão do processamento não representa validação automática;
- os resultados devem passar por revisão técnica;
- podem existir componentes que necessitem adaptação manual;
- informações sensíveis não devem ser submetidas ao sistema;
- falhas e inconsistências devem ser reportadas para análise.

---

## 10. Modelo de comunicação de risco crítico

### Assunto

Risco crítico identificado — RISC Convert

### Identificação

**Risco:** R01 — Conversão funcionalmente incorreta

**Severidade:** Crítica

### Situação

Foi identificado risco de o código convertido apresentar comportamento diferente da aplicação original, mesmo após conclusão do processo de build.

### Impacto potencial

A ocorrência pode resultar em falhas funcionais, retrabalho, atraso na entrega e redução da confiabilidade da conversão.

### Ação definida

Será aplicado o processo de validação em múltiplas camadas, incluindo build, testes automatizados, análise de logs, comparação funcional e revisão técnica.

### Responsável

Líder Técnico

### Próxima atualização

A próxima atualização será realizada após a conclusão das validações e análise dos resultados.

---

## 11. Comunicação de status do projeto

O relatório periódico de status deverá conter:

### Status geral

- Verde: projeto dentro do planejamento;
- Amarelo: existem riscos ou impedimentos relevantes;
- Vermelho: existe impacto significativo em prazo, qualidade, custo ou entrega.

### Informações mínimas

- entregas concluídas;
- atividades em andamento;
- próximos passos;
- riscos prioritários;
- impedimentos;
- decisões necessárias;
- indicadores relevantes.

---

## 12. Uso da IA Generativa na comunicação

A Inteligência Artificial Generativa poderá ser utilizada como apoio na elaboração e revisão das comunicações do projeto.

Entre os possíveis usos estão:

- resumir informações técnicas;
- adaptar linguagem para diferentes stakeholders;
- estruturar relatórios de status;
- organizar informações sobre riscos;
- sugerir formatos de comunicação;
- revisar clareza e consistência dos textos.

As informações geradas ou revisadas pela IA deverão passar por validação humana antes de serem compartilhadas.

---

## 13. Cuidados no uso da IA

Durante a utilização da IA para apoiar a comunicação, deverão ser observados os seguintes cuidados:

- não inserir credenciais, segredos ou dados confidenciais;
- revisar informações factuais;
- evitar o compartilhamento automático de textos gerados;
- adaptar a linguagem ao público;
- validar classificações de risco;
- garantir que decisões atribuídas à equipe tenham sido realmente tomadas;
- manter a responsabilidade humana pela comunicação final.

---

## 14. Considerações finais

Um plano de comunicação adequado contribui diretamente para a gestão de riscos do RISC Convert.

A identificação de um risco não é suficiente se a informação não chegar às pessoas responsáveis por decidir ou agir sobre ele.

Por isso, o projeto considera a comunicação como parte integrante da gestão de riscos, utilizando a Inteligência Artificial Generativa como ferramenta de apoio, mas mantendo a revisão e a tomada de decisão sob responsabilidade humana.
