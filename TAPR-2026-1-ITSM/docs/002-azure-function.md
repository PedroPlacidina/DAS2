# ADR-003: Adoção do Azure Functions para processamento dos dados

**Status:** Aceito  |  **Data:** 2026-08-27  |  **Autores:** Equipe TAPR

## Contexto

O Sistema TAPR precisa realizar a extração e o processamento dos dados utilizados na análise de ITSM.

A solução possui diferentes conjuntos de dados relacionados ao atendimento de suporte, como chamados, analistas, categorias, SLA, CSAT e outras informações utilizadas na geração dos indicadores.

Era necessário definir uma forma de executar essas tarefas sem a necessidade de manter permanentemente um servidor dedicado para o processamento.

## Decisão

Foi adotado o **Azure Functions** como plataforma para execução das funções responsáveis pela extração e processamento dos dados do Sistema TAPR.

As funções são implementadas em **Python** e organizadas de acordo com as diferentes necessidades de extração e processamento dos dados.

Entre os processos existentes no projeto estão funções relacionadas à extração de:

- Analistas;
- Categorias;
- Chamados;
- SLA;
- CSAT;
- Outros dados utilizados pelo sistema.

As Azure Functions realizam o processamento necessário e integram-se aos demais componentes da arquitetura, incluindo o Azure SQL Database e o Azure Blob Storage.

A utilização do modelo serverless permite que a infraestrutura necessária para execução das funções seja gerenciada pelo próprio Azure.

## Consequências

(+) Não é necessário manter um servidor dedicado permanentemente para executar as funções.

(+) Permite organizar o processamento em funções independentes.

(+) Possui integração com outros serviços utilizados na arquitetura Azure.

(-) Cria dependência do serviço Azure Functions.

## Alternativas rejeitadas

- **Máquina virtual com aplicação Python executando continuamente**: foi rejeitada porque exigiria gerenciamento do sistema operacional, servidor, atualizações e disponibilidade da infraestrutura.

## Links

- Substitui: Não se aplica.

- Relacionado: `adr001-cloud.md`, `adr002-database.md`

- Evidências: `src/function_app.py`, módulos de extração em `src/` e `docs/justificativa-tecnologica.md`
