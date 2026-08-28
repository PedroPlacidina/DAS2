# ADR-001: Adoção do Microsoft Azure como plataforma de nuvem

**Status:** Aceito  |  **Data:** 2026-08-27  |  **Autores:** Equipe TAPR

## Contexto

O Sistema TAPR necessita de uma infraestrutura capaz de executar o processamento dos dados de ITSM, armazenar os dados utilizados pela aplicação e disponibilizar os resultados para análise.

A solução precisa trabalhar com diferentes componentes, incluindo processamento de dados, armazenamento de arquivos, banco de dados e ferramenta de visualização. Dessa forma, seria necessário utilizar uma infraestrutura que permitisse integrar esses diferentes serviços de maneira organizada.

## Decisão

Foi adotado o **Microsoft Azure** como plataforma de computação em nuvem para hospedar e disponibilizar os principais serviços utilizados pelo Sistema TAPR.

A arquitetura utiliza serviços gerenciados do Azure, incluindo:

- Azure Functions para execução do processamento e das funções de extração;
- Azure SQL Database para armazenamento dos dados;
- Azure Blob Storage para armazenamento dos dados brutos.

A utilização desses serviços permite que os diferentes componentes da solução sejam integrados dentro do mesmo ambiente de nuvem.

## Consequências

(+) Permite utilizar serviços gerenciados sem a necessidade de administrar servidores físicos.

(+) Facilita a integração entre Azure Functions, Azure SQL Database e Azure Blob Storage.

(+) Permite escalar os recursos de acordo com a necessidade da aplicação.

(-) Cria dependência do ecossistema Microsoft Azure.

## Alternativas rejeitadas

- **AWS**: foi rejeitada devido à menor integração com os serviços Microsoft utilizados no projeto e à necessidade de utilizar diferentes serviços equivalentes para compor a arquitetura

## Links

- Substitui: Não se aplica.

- Relacionado: `adr003-azure-function.md`, `adr002-database.md`, `adr004-power-bi.md`

- Evidências: `docs/justificativa-tecnologica.md` e `docs/Arquitetura.png`
