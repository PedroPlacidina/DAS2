# ADR-003: Adoção do Power BI para visualização dos indicadores de ITSM

**Status:** Aceito  |  **Data:** 2026-08-27  |  **Autores:** Pedro Henrique Placidina Maria

## Contexto

O Sistema TAPR tem como objetivo transformar dados de suporte de TI em informações úteis para análise e tomada de decisão. A organização possui dados relacionados a chamados, SLA, filas, categorias, analistas, clientes e satisfação dos usuários.

## Decisão

Foi adotado o **Microsoft Power BI** como ferramenta de e visualização dos dados do Sistema TAPR.

O Power BI será utilizado para consumir os dados armazenados no Azure SQL Database e disponibilizar dashboards e indicadores relacionados ao atendimento de TI.

## Consequências

(+) Permite a criação de dashboards interativos para análise dos indicadores de ITSM.

(+) Possui integração nativa com o Azure SQL Database utilizado pelo projeto.

(-) Cria dependência de uma ferramenta proprietária do ecossistema Microsoft.

## Alternativas rejeitadas

As duas alternativas avaliadas foram **Streamlit** e **Metabase**.

- **Streamlit:** excelente para criar dashboards analíticos com Python de forma rápida. Porém, exige um servidor web em execução contínua para hospedar a aplicação (custo adicional de infraestrutura), não possui conector nativo para Azure SQL com atualização agendada, e sua capacidade de compartilhamento enterprise é limitada. Para um projeto com usuários finais não-técnicos, o Streamlit adiciona complexidade desnecessária.

- **Metabase:** ferramenta open source de BI com interface amigável e boa para exploração ad-hoc de dados. Contudo, na versão gratuita exige infraestrutura própria para hospedar (servidor Linux ou Docker), o que adiciona um novo recurso a gerenciar. A versão Cloud tem custo e, mesmo assim, a integração com o ecossistema Azure não é tão fluida quanto a do Power BI. Dado que a CorpTech já investe na Azure, o Power BI representa a escolha com menor atrito operacional.


## Links

- Substitui: Não se aplica.

- Relacionado: `004-database.md`

- Evidências: `docs/justificativa-tecnologica.md` e `TRABALHOTAPR.pbix`
