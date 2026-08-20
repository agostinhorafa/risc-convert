# Requisitos Funcionais — RISC Convert

## 1. Objetivo

Este documento apresenta os requisitos funcionais identificados para o cenário fictício RISC Convert.

Os requisitos descrevem os comportamentos e funcionalidades que a plataforma deverá oferecer aos seus usuários durante o processo de submissão, análise, conversão, validação e disponibilização de aplicações convertidas com apoio de Inteligência Artificial Generativa.

---

## 2. Requisitos Funcionais

### RF01 — Submeter projeto para conversão

O sistema deve permitir que o usuário submeta um projeto de software para conversão.

A submissão poderá ocorrer por meio de:

* upload de arquivo compactado;
* endereço de um repositório de código compatível com a plataforma.

---

### RF02 — Validar o projeto submetido

O sistema deve realizar uma validação inicial do projeto antes de iniciar a conversão.

A validação deve verificar, no mínimo:

* existência de arquivos;
* formato da entrada;
* estrutura mínima do projeto;
* presença de arquivos inválidos ou não suportados.

Caso a validação falhe, o usuário deve ser informado antes do início do processamento.

---

### RF03 — Analisar a estrutura do projeto

O sistema deve analisar automaticamente a estrutura do projeto submetido.

A análise deve identificar, quando possível:

* arquivos de código-fonte;
* módulos;
* bibliotecas;
* dependências;
* arquivos de configuração;
* componentes relevantes para a conversão.

---

### RF04 — Identificar dependências incompatíveis

O sistema deve identificar dependências, bibliotecas ou componentes que não possam ser convertidos automaticamente.

Os itens incompatíveis devem ser registrados e apresentados ao usuário.

---

### RF05 — Iniciar o processo de conversão

Após a validação inicial, o sistema deve permitir o início do processo de conversão.

A conversão deve utilizar Inteligência Artificial Generativa como apoio para transformar o código da aplicação de origem para a tecnologia de destino definida para o processamento.

---

### RF06 — Processar o projeto em etapas

O sistema deve executar a conversão em etapas controladas.

O processamento deve permitir o acompanhamento das principais fases, como:

1. análise;
2. preparação;
3. conversão;
4. validação;
5. finalização.

---

### RF07 — Exibir o progresso da conversão

O sistema deve permitir que o usuário acompanhe o status da conversão.

O status deve indicar, no mínimo:

* aguardando processamento;
* em análise;
* em conversão;
* em validação;
* concluída;
* concluída com ressalvas;
* falha.

---

### RF08 — Registrar logs da execução

O sistema deve registrar informações relevantes durante o processo de conversão.

Os logs devem permitir identificar:

* etapas executadas;
* arquivos processados;
* erros encontrados;
* dependências incompatíveis;
* tentativas adicionais;
* resultado das validações.

---

### RF09 — Executar validação de build

Após a conversão, o sistema deve executar uma validação de build ou compilação sempre que a tecnologia de destino permitir.

O resultado deve ser registrado como parte da validação da conversão.

---

### RF10 — Executar testes automatizados

O sistema deve permitir a execução de testes automatizados associados ao projeto convertido quando esses testes estiverem disponíveis ou forem compatíveis com o processo de validação.

O resultado dos testes deve ser registrado e apresentado ao usuário.

---

### RF11 — Apresentar falhas de validação

Caso ocorram falhas durante a validação, o sistema deve informar ao usuário quais etapas não foram concluídas com sucesso.

Sempre que possível, a plataforma deve apresentar:

* etapa que falhou;
* mensagem de erro;
* arquivo ou componente relacionado;
* orientação para revisão manual.

---

### RF12 — Preservar o progresso da conversão

O sistema deve armazenar o estado das etapas concluídas durante o processamento.

Caso ocorra uma interrupção recuperável, o sistema deve permitir a retomada da conversão sem reprocessar etapas já concluídas, quando tecnicamente possível.

---

### RF13 — Disponibilizar artefatos convertidos

Ao final do processamento, o sistema deve disponibilizar os artefatos gerados para download.

Os artefatos devem estar associados ao resultado da conversão correspondente.

---

### RF14 — Disponibilizar relatório da conversão

O sistema deve gerar um relatório resumindo o resultado do processamento.

O relatório deve apresentar, quando aplicável:

* resultado geral da conversão;
* resultado do build;
* resultado dos testes;
* dependências incompatíveis;
* arquivos que apresentaram erro;
* itens que necessitam de revisão manual.

---

### RF15 — Diferenciar conversão concluída de conversão validada

O sistema deve diferenciar uma conversão cujo processamento foi concluído de uma conversão considerada tecnicamente validada.

A conclusão do processamento não deve implicar automaticamente que o código convertido está pronto para uso em produção.

---

## 3. Observações

Os requisitos apresentados neste documento foram definidos para o cenário acadêmico do RISC Convert.

Algumas informações específicas ainda dependem de definição, como:

* tecnologias de origem suportadas;
* tecnologias de destino suportadas;
* limite máximo de tamanho dos projetos;
* tempo máximo aceitável para processamento;
* política de retenção dos artefatos;
* critérios exatos para considerar uma conversão validada.

Esses pontos serão registrados separadamente como lacunas ou decisões pendentes, evitando tratá-los como requisitos definitivos sem informação suficiente.
