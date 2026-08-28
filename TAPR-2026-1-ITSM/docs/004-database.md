# ADR-004: Adoção do Azure SQL Database como banco de dados do Sistema TAPR

**Status:** Aceito  |  **Data:** 2026-08-27  |  **Autores:** Pedro Henrique Placidina Maria

## Contexto

O Sistema TAPR precisa armazenar e consultar dados relacionados ao atendimento de suporte de TI. Esses dados incluem informações de chamados, analistas, clientes, categorias, filas, SLA, histórico de status e avaliações de satisfação.

## Decisão

Foi adotado o **Azure SQL Database** como banco de dados relacional utilizado pelo Sistema TAPR.

O Azure SQL Database possui dois papéis na arquitetura:

1. **Fonte de dados mockada:** utilizada para simular a base de dados de produção relacionada ao Jira Service Management.

2. **Destino analítico:** utilizado para armazenar os dados após o processamento realizado pelas Azure Functions, incluindo informações e métricas utilizadas na análise de ITSM.

## Consequências

(+) Utilização de um banco de dados relacional adequado para dados estruturados de ITSM.

(+) Permite utilização de SQL, JOINs e agregações para consultas analíticas.

(-) Cria dependência do serviço Azure SQL Database e do ecossistema Microsoft Azure.

(-) O custo do serviço pode aumentar conforme o volume de dados e os recursos computacionais utilizados.

(-) A utilização de uma base mockada não representa completamente todas as características e restrições do ambiente real do Jira Service Management.

## Alternativas rejeitadas

## Links

- Substitui: Não se aplica.

- Relacionado: `003-power-bi.md`

- Evidências: `docs/justificativa-tecnologica.md`, `docs/Arquitetura.png` e código em `src/`
