# UC03 — Manter questionários e competências

Sistema web de feedback e desenvolvimento de competências.

Versão 0.1, 17/11/2026. Responsável: Kezer. Situação: aguardando validação do grupo.

## 1 Identificação

| Campo | Conteúdo |
|---|---|
| Identificador | UC03 |
| Nome | Manter questionários e competências |
| Atores primários | RH, Gestor |
| Atores secundários | — |
| Requisitos atendidos | RF04, RF05 e os propostos RF23, RF24, RF25, RF26 |
| Regras aplicáveis | RN04; RN05 por consequência |
| Frequência | Baixa. O catálogo é montado na implantação e revisado a cada ciclo formal, de três a quatro meses |
| Prioridade | Alta — UC08 depende deste caso de uso para existir |

## 2 Descrição

Mantém os dois catálogos que alimentam o feedback formal: as **competências**, que descrevem o que se espera da pessoa, e os **questionários**, que são conjuntos reutilizáveis de competências usados nas rodadas de avaliação.

O RH mantém as competências da organização e indica quais são fixas de cada cargo. O gestor pode acrescentar competência específica a um colaborador do seu time, além das do cargo. O RH também mantém modelos de questionário, para que o gestor não precise montar a lista do zero a cada rodada.

A separação entre catálogo e cópia publicada é o ponto central deste caso de uso: **alterar o catálogo nunca altera uma rodada já aberta**. Sem isso, o gráfico de evolução do RF22 compara medições feitas com réguas diferentes.

## 3 Origem

Vem da entrevista com a especialista do domínio. Ela descreveu competências fixas por cargo e competências específicas de uma pessoa, e, quando perguntada sobre guardar uma lista de parâmetros reutilizável, respondeu que achava interessante, acrescentando que trazer os feedbacks anteriores ajuda a ver a evolução. Também descreveu a necessidade de traduzir uma competência ampla em indicadores concretos antes de avaliar.

## 4 Pré-condições

1. O ator está autenticado (UC01).
2. Para as operações de competência fixa de cargo e de questionário, o ator tem perfil RH.
3. Para competência específica de colaborador, o ator é o gestor do time do colaborador.
4. Para vincular competência a cargo, existe pelo menos um cargo cadastrado (UC02).

## 5 Pós-condições

| Situação | Estado resultante |
|---|---|
| Sucesso na criação ou alteração | Item gravado e disponível para novas rodadas; rodadas já abertas permanecem inalteradas |
| Sucesso na desativação | Item deixa de aparecer na montagem de novas rodadas, mas continua visível no histórico e nos resultados anteriores |
| Falha | Nenhuma alteração é gravada e o ator recebe a mensagem do campo e da condição inválida |

## 6 Fluxo principal — manter competências

| # | Ator | Sistema |
|---|---|---|
| 1 | O RH acessa o catálogo de competências | Exibe as competências ativas, com nome, descrição, indicador sugerido e cargos vinculados |
| 2 | O RH escolhe criar uma competência | Exibe o formulário com nome, descrição e indicador sugerido |
| 3 | O RH preenche e confirma | Valida os campos obrigatórios e a unicidade do nome, grava e exibe a competência na lista |
| 4 | O RH abre a competência e vincula um ou mais cargos | Grava os vínculos e passa a exibir a competência como fixa para todo colaborador daqueles cargos |
| 5 | O RH encerra | Mantém o catálogo atualizado |

O indicador sugerido é um texto livre que acompanha a competência, por exemplo "nota do cliente acima de 4" para comunicação. Serve para orientar quem for montar o objetivo do plano de ação (RF12) e evitar a competência ampla demais que a cliente criticou na entrevista.

## 7 Fluxo principal — manter questionários

| # | Ator | Sistema |
|---|---|---|
| 1 | O RH acessa o catálogo de questionários | Exibe os modelos ativos, com nome, finalidade, quantidade de competências e data da última alteração |
| 2 | O RH escolhe criar um questionário | Exibe o formulário com nome, finalidade e seleção de competências do catálogo |
| 3 | O RH seleciona as competências e define a ordem | Valida que há pelo menos uma competência ativa selecionada e que não há repetição |
| 4 | O RH confirma | Grava o modelo e o disponibiliza na criação de rodadas (UC08) |

## 8 Fluxos alternativos

**FA01 — Gestor adiciona competência específica a um colaborador (RF05).**
No passo 1 do fluxo da seção 6, o ator é o gestor e acessa o colaborador pelo painel "Meu time". O sistema exibe as competências fixas do cargo, em modo somente leitura, e a lista de competências específicas. O gestor escolhe uma competência do catálogo e a vincula ao colaborador. O sistema grava o vínculo e passa a oferecer essa competência quando o colaborador for avaliado ou tiver plano de ação.

**FA02 — Alterar competência já usada.**
No passo 3, se a competência já constar de alguma rodada aberta ou encerrada, o sistema avisa que a alteração vale apenas para novas rodadas e pede confirmação. Confirmada, a alteração afeta somente o catálogo.

**FA03 — Desativar competência.**
O RH desativa uma competência em vez de excluí-la. O sistema remove a competência das listas de seleção, mantém os vínculos e resultados históricos e informa em quantos questionários ativos ela era usada, para que o RH revise esses modelos.

**FA04 — Duplicar questionário.**
No passo 2 do fluxo da seção 7, o RH escolhe duplicar um modelo existente. O sistema abre o formulário preenchido com as competências do original e exige um nome diferente.

**FA05 — Ajuste do questionário dentro da rodada (RF24).**
Em UC08, o gestor parte de um modelo e remove ou acrescenta competências apenas para aquela rodada. O sistema grava o ajuste na rodada e **não** altera o modelo de origem.

## 9 Fluxos de exceção

**FE01 — Nome repetido.** O sistema rejeita, aponta o campo e mantém o restante do formulário preenchido.

**FE02 — Questionário sem competência.** O sistema impede gravar um modelo com zero competências ativas e informa o motivo.

**FE03 — Competência desativada dentro de questionário ativo.** Ao abrir uma rodada com esse modelo, o sistema apresenta a divergência e exige que o gestor atualize a seleção explicitamente. A abertura não remove a competência em silêncio.

**FE04 — Gestor fora do seu time.** Em FA01, se o colaborador não for do time do gestor, o sistema rejeita a operação conforme RN04, inclusive em chamada direta à API.

**FE05 — Perfil sem permissão.** Colaborador sem perfil de gestor ou RH não acessa este caso de uso; a tentativa é registrada na auditoria.

## 10 Regras específicas

| ID | Regra |
|---|---|
| RE01 | Competência fixa é vinculada ao **cargo**, não à pessoa. Mudar o cargo do colaborador muda as competências fixas que valem para ele daqui em diante, sem reescrever resultados anteriores |
| RE02 | Competência específica é vinculada à **pessoa** e vale além das do cargo, nunca no lugar delas |
| RE03 | Nenhum item do catálogo é excluído fisicamente; a retirada de uso é feita por desativação |
| RE04 | Na abertura da rodada, o sistema grava uma **cópia** do questionário publicado: texto da competência, escala e ordem. A cópia é imutável |
| RE05 | Duas rodadas só entram na mesma série do gráfico de evolução quando a competência de origem, o texto e a escala da cópia forem iguais |
| RE06 | Um mesmo questionário pode ser usado por rodadas diferentes; uma rodada usa um único questionário |

RE04 e RE05 reaproveitam, com os IDs novos, o mecanismo de *snapshot* já descrito nos RF09, RN05 e RN11 da especificação IEEE 830 v0.1. É a parte daquele documento que deve sobreviver à reescrita.

## 11 Requisitos propostos

Decorrem deste caso de uso e **ainda não constam** da lista geral. Precisam ser aprovados pelo responsável por ela.

| ID | Requisito |
|---|---|
| RF23 | O RH deve manter modelos de questionário, com nome, finalidade e um conjunto ordenado de competências do catálogo, reutilizáveis em várias rodadas de avaliação |
| RF24 | Ao criar uma rodada, o gestor deve partir de um modelo de questionário e poder ajustar as competências apenas daquela rodada, sem alterar o modelo de origem |
| RF25 | Ao abrir a rodada, o sistema deve gravar uma cópia imutável do questionário publicado, usada na validação das respostas e nas análises históricas |
| RF26 | Alterar ou desativar competência e questionário no catálogo não deve modificar rodadas já abertas ou encerradas |

## 12 Protótipo

Telas previstas, a desenhar no Figma: **Catálogo de competências** (lista, formulário, vínculo com cargos), **Competências do colaborador** (dentro de "Meu time", para FA01) e **Catálogo de questionários** (lista, formulário com seleção ordenada, duplicar).

## 13 Pontos a validar

1. Escala por competência ou escala única da rodada. A lista geral fixa 1 a 5 para toda a rodada (RF17), decisão do grupo. O IEEE 830 v0.1 admite escala por pergunta. A segunda opção é mais flexível e mais cara; a primeira simplifica o gráfico de evolução.
2. Competência e pergunta são a mesma coisa nesta versão. Se o grupo quiser várias perguntas por competência, muda o modelo de dados e este caso de uso.
3. Quem mantém o questionário: aqui é o RH, por simetria com o cadastro de competências. A cliente disse que o RH pode fazer, mas que o maior poder costuma ser do gestor. Decidir junto com a pendência equivalente da lista geral sobre quem cria a rodada.
