# Sistema de criação e gerenciamento de feedbacks

Documentação inicial para um sistema de avaliação mútua, com seleção de pares ou times, questionários organizados em grupos de parâmetros e histórico por usuário. Na seleção de times, todos os integrantes elegíveis de cada time avaliam uns aos outros nos dois sentidos.

`PROF` significa profissional. O campo `score` define o tipo de avaliação do parâmetro: escala de 0 a 10, escala de 0 a 5 ou booleano. Dados não são excluídos fisicamente; são desativados ou cancelados, conforme a entidade.

- [Especificação de Requisitos IEEE 830](docs/especificacao-requisitos-ieee830.md): escopo, perfis, requisitos, regras, critérios de aceitação e rastreabilidade.
- [Domínio e modelo de domínio](docs/dominio.md): conceitos, responsabilidades, fluxo e relações conceituais.
- [Modelo Entidade Relacionamento](docs/modelo-entidade-relacionamento.md): entidades, cardinalidades, restrições e diagramas Mermaid.
- [Dicionário de dados](docs/dicionario-de-dados.md): atributos, tipos propostos, validações e correspondência com os campos originais.

Versão 0.1, de 20 de outubro de 2026. As decisões propostas e as questões pendentes estão identificadas na especificação. Este repositório contém documentação; não representa uma implementação do sistema.

Os diagramas estão em Mermaid e podem ser visualizados no GitHub ou em um editor compatível.
