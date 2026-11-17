# Matriz de Rastreabilidade

Sistema web de feedback e desenvolvimento de competências.

Versão 0.1, 17/11/2026. Responsável: Kezer. Situação: aguardando validação do grupo.

Base: [`requisitos.md`](requisitos.md) v0.3 (RF01–RF22, RN01–RN06, RNF01–RNF06) e [`casos-de-uso.drawio`](../casos-de-uso/casos-de-uso.drawio). Todos os IDs desta matriz são os da lista geral; nada foi renumerado aqui.

## 1 Convenções

Duas direções são registradas, conforme a convenção adotada pelo grupo:

- **Rastreabilidade horizontal:** liga artefatos de **níveis diferentes** do mesmo ciclo — necessidade → requisito → caso de uso → regra → critério de verificação. Responde a "este requisito veio de onde e é verificado como?".
- **Rastreabilidade vertical:** liga itens do **mesmo nível** — requisito que depende de requisito, requisito que deriva de requisito, e a projeção do requisito sobre os artefatos de projeto (entidade do MER, tela do protótipo). Responde a "se eu mudar este requisito, o que quebra junto?".

Prefixos: `FNT` fonte, `NEC` necessidade, `RF` requisito funcional, `RN` regra de negócio, `RNF` requisito não funcional, `UC` caso de uso, `CV` critério de verificação, `LAC` lacuna.

## 2 Fontes

| ID | Fonte | Situação |
|---|---|---|
| FNT01 | Enunciado da disciplina (PDF `trabalho_da_disciplina_de_domnio.pdf`) | Disponível |
| FNT02 | Entrevista com a professora, na condição de especialista do domínio (transcrição da reunião) | Disponível; transcrição ainda não versionada em `docs/` |
| FNT03 | Anotações do Caique durante a entrevista | Disponível |
| FNT04 | Decisão do grupo (sem origem externa) | Registrada na seção 2 de `requisitos.md` |
| FNT05 | Entrevistas do grupo (2, com nome, função e telefone) | **Pendente** — responsável: Vitória |
| FNT06 | Questionários aplicados (2, com respostas) | **Pendente** — responsável: P4 |
| FNT07 | Pesquisa de sistema análogo | **Pendente** — responsável: Gabriel T. A tabela da seção 8 de `requisitos.md` declara-se não verificada e não substitui esta fonte |

Enquanto FNT05, FNT06 e FNT07 não existirem, as colunas de origem desta matriz apontam quase sempre para FNT02, o que é um risco de cobertura a declarar na apresentação.

## 3 Necessidades

Extraídas de FNT01 a FNT03. São o nível acima dos requisitos.

| ID | Necessidade | Origem |
|---|---|---|
| NEC01 | Centralizar o registro dos feedbacks, hoje disperso em papel, Excel ou na memória do gestor | FNT02 |
| NEC02 | Garantir que todo feedback se apoie em fatos, reduzindo subjetividade e dando rastreabilidade | FNT02, FNT03 |
| NEC03 | Apoiar a estrutura do feedback positivo e do construtivo, para que um feedback mal dado não destrua a pessoa | FNT02 |
| NEC04 | Saber se o colaborador efetivamente melhorou depois do feedback | FNT02 |
| NEC05 | Planejar o feedback formal com objetivos, competências e indicadores, por cargo e por pessoa | FNT02, FNT03 |
| NEC06 | Permitir avaliação em várias direções: gestor, pares, 360 e autoavaliação | FNT01, FNT02 |
| NEC07 | Preservar o feedback como registro oficial, sem exclusão | FNT02 |
| NEC08 | Dar ao gestor visão gerencial do time | FNT02 |
| NEC09 | Mostrar a evolução da pessoa ao longo do tempo | FNT02, FNT03 |
| NEC10 | Controlar acesso e proteger dados pessoais, com anonimato parametrizável entre pares | FNT01, FNT02 |

## 4 Matriz horizontal — requisito como entrada

| RF | Necessidade | Origem | UC | Regras | RNF | Verificação |
|---|---|---|---|---|---|---|
| RF01 | NEC10 | FNT02 | UC01 | RN04 | RNF03 | CV01 |
| RF02 | NEC01, NEC07 | FNT02 | UC02 | RN04 | RNF04 | CV02 |
| RF03 | NEC08 | FNT02 | UC02 | RN04 | — | CV02 |
| RF04 | NEC05 | FNT02 | UC03 | — | — | CV03 |
| RF05 | NEC05 | FNT02, FNT03 | UC03 | — | — | CV03 |
| RF06 | NEC01, NEC02, NEC03 | FNT02, FNT03 | UC04 | RN01, RN03 | RNF05 | CV04 |
| RF07 | NEC03 | FNT02 | UC04 | RN01 | RNF05 | CV05 |
| RF08 | NEC07 | FNT02 | UC04, UC05 | RN02 | RNF04 | CV06 |
| RF09 | NEC01 | FNT02 | UC04 | RN04 | — | CV07 |
| RF10 | NEC04 | FNT02 | UC04, UC07 | — | — | CV08 |
| RF11 | NEC05 | FNT02 | UC06 | — | — | CV09 |
| RF12 | NEC04, NEC05 | FNT02 | UC07 | — | — | CV10 |
| RF13 | NEC04 | FNT02 | UC07 | — | — | CV10 |
| RF14 | NEC04 | FNT02 | UC07 | — | — | CV11 |
| RF15 | NEC04 | FNT02 | UC07 | — | — | CV12 |
| RF16 | NEC05, NEC06, NEC10 | FNT01, FNT02 | UC08 | RN03, RN05 | — | CV13 |
| RF17 | NEC06, NEC02 | FNT01, FNT02 | UC09 | RN01, RN03 | — | CV14 |
| RF18 | NEC06 | FNT02 | UC08 | RN06 | — | CV15 |
| RF19 | NEC06, NEC09 | FNT02 | UC08, UC11 | RN04 | — | CV16 |
| RF20 | NEC09 | FNT02 | UC05 | RN04 | — | CV17 |
| RF21 | NEC08 | FNT02 | UC10 | RN04 | — | CV18 |
| RF22 | NEC09 | FNT01, FNT02 | UC11 | RN04 | — | CV19 |

Requisitos propostos na especificação de UC03, ainda **fora** da lista geral:

| RF | Necessidade | Origem | UC | Verificação |
|---|---|---|---|---|
| RF23 | NEC05 | FNT02 | UC03 | CV20 |
| RF24 | NEC05, NEC06 | FNT02 | UC03, UC08 | CV21 |
| RF25 | NEC07, NEC09 | FNT02 | UC03, UC08, UC11 | CV22 |
| RF26 | NEC07 | FNT02 | UC03 | CV22 |

## 5 Matriz horizontal inversa — cobertura

### 5.1 Necessidade → requisitos

| Necessidade | Requisitos | Cobertura |
|---|---|---|
| NEC01 | RF02, RF06, RF09 | Completa |
| NEC02 | RF06, RF17 | Completa |
| NEC03 | RF06, RF07 | Completa |
| NEC04 | RF10, RF12, RF13, RF14, RF15 | Completa |
| NEC05 | RF04, RF05, RF11, RF12, RF16, RF23, RF24 | Completa apenas se RF23 e RF24 forem aceitos |
| NEC06 | RF16, RF17, RF18, RF19 | Completa |
| NEC07 | RF02, RF08, RF25, RF26 | **Parcial** — ver LAC01 |
| NEC08 | RF03, RF21 | Completa |
| NEC09 | RF19, RF20, RF22 | **Parcial** — ver LAC02 |
| NEC10 | RF01, RF16 | **Parcial** — ver LAC03 |

### 5.2 Caso de uso → requisitos

| UC | Nome | Requisitos | Ator principal |
|---|---|---|---|
| UC01 | Fazer login | RF01 | Colaborador, Gestor, RH |
| UC02 | Manter usuários e times | RF02, RF03 | RH |
| UC03 | Manter questionários e competências | RF04, RF05, RF23–RF26 | RH, Gestor |
| UC04 | Dar feedback | RF06, RF07, RF08, RF09, RF10 | Colaborador, Gestor |
| UC05 | Consultar "Meu desenvolvimento" | RF08, RF09, RF20 | Colaborador |
| UC06 | Agendar conversa de feedback | RF11 | Gestor |
| UC07 | Gerenciar plano de ação | RF12, RF13, RF14, RF15 | Gestor, Colaborador |
| UC08 | Conduzir rodada de avaliação | RF16, RF18, RF19 | Gestor |
| UC09 | Responder rodada de avaliação | RF17 | Colaborador, Gestor |
| UC10 | Consultar painel "Meu time" | RF21 | Gestor |
| UC11 | Consultar histórico de feedbacks | RF22 | Gestor, RH |

Nenhum RF da lista geral ficou sem caso de uso, e nenhum caso de uso ficou sem RF.

### 5.3 Regra de negócio → requisitos

| RN | Requisitos que a aplicam |
|---|---|
| RN01 | RF06, RF07, RF17 |
| RN02 | RF08 |
| RN03 | RF06, RF16, RF17 |
| RN04 | RF01, RF02, RF09, RF19, RF20, RF21, RF22 |
| RN05 | RF16 |
| RN06 | RF18 |

## 6 Critérios de verificação

| CV | Critério | Método | Origem |
|---|---|---|---|
| CV01 | Um perfil não acessa tela de outro perfil, inclusive por URL direta | Teste de autorização | — |
| CV02 | Desativar usuário com histórico preserva seus feedbacks; nenhuma operação apaga fisicamente | Teste + inspeção do banco | CA01 do IEEE 830 |
| CV03 | Competência fixa de cargo aparece para todos daquele cargo; competência específica só para o colaborador indicado | Teste funcional | — |
| CV04 | Enviar feedback sem preencher o fato é rejeitado com erro no campo | Teste funcional | — |
| CV05 | Trocar o tipo de positivo para construtivo troca a dica exibida, sem apagar o texto já digitado | Teste funcional | — |
| CV06 | Feedback enviado não oferece editar nem excluir; comentário do emissor e do receptor é aceito | Teste funcional | CA08 |
| CV07 | O receptor vê o feedback no painel e recebe notificação na plataforma | Teste funcional | — |
| CV08 | Feedback construtivo exibe "Criar plano de ação"; positivo não exibe | Teste funcional | — |
| CV09 | Conversa agendada gera lembrete para os dois antes da data | Teste com relógio simulado | — |
| CV10 | Gestor cria o plano; o colaborador consegue alterar as ações do mesmo plano | Teste de autorização | — |
| CV11 | Na data do check-in, os dois são lembrados; o comentário fica registrado com autor e data | Teste com relógio simulado | — |
| CV12 | Encerrar com "não melhorou" oferece novo feedback; encerrar com "melhorou" não oferece | Teste funcional | — |
| CV13 | Rodada com anonimato ligado não exibe o autor das respostas entre pares; a do gestor continua identificada | Teste funcional | — |
| CV14 | Cada participante recebe a si mesmo na lista; nota fora de 1 a 5 é rejeitada | Teste funcional | CA07 |
| CV15 | A lista de respondentes e de faltantes bate com o estado real das respostas | Teste funcional | — |
| CV16 | Com autoavaliação 5 e notas 3 e 3 dos pares, o resultado mostra 5 contra média 3 | Teste de cálculo | CA10 |
| CV17 | "Meu desenvolvimento" mostra apenas o que é do próprio usuário | Teste de autorização | CA02 |
| CV18 | "Meu time" lista quem não recebeu feedback nos últimos 6 meses | Teste de cálculo com massa datada | — |
| CV19 | O gráfico só compara rodadas cuja competência e escala sejam as mesmas | Teste de cálculo | CA11 |
| CV20 | Modelo de questionário criado pelo RH aparece na criação de rodada | Teste funcional | — |
| CV21 | Ajustar o questionário dentro da rodada não altera o modelo de origem | Teste funcional | CA04 |
| CV22 | Alterar ou desativar competência no catálogo não altera rodada já publicada | Teste funcional | CA04, CA11 |

Os CV marcados com origem reaproveitam critérios já escritos na seção 3.6 da [especificação IEEE 830](especificacao-requisitos-ieee830.md). Eles continuam válidos para a parte de rodada de avaliação, mesmo com a reescrita pendente daquele documento.

## 7 Matriz vertical — dependências entre requisitos

| RF | Depende de | Motivo |
|---|---|---|
| RF04, RF05 | RF02, RF03 | Competência se liga a cargo e a colaborador cadastrado |
| RF06 | RF01, RF02 | Emissor e receptor precisam existir e estar autenticados |
| RF07 | RF06 | A dica é do campo do RF06 |
| RF08 | RF06 | Só existe imutabilidade depois do envio |
| RF09 | RF06 | Notifica o receptor do feedback criado |
| RF10 | RF06, RF12 | Liga o feedback construtivo ao plano |
| RF13 | RF12 | Edita ações do plano criado |
| RF14, RF15 | RF12 | Check-in e encerramento são do plano |
| RF15 | RF06 | "Não melhorou" origina novo feedback |
| RF16 | RF03, RF04, RF23 | Participantes vêm do time; competências vêm do catálogo ou do modelo |
| RF17 | RF16 | Só se responde rodada aberta |
| RF18, RF19 | RF16, RF17 | Dependem das respostas da rodada |
| RF19 | RF12 | O resultado pode originar plano de ação |
| RF20 | RF06, RF12, RF17 | Agrega feedbacks, planos e resultados |
| RF21 | RF03, RF06, RF12, RF16 | Agrega por time |
| RF22 | RF06, RF17, RF25 | Série histórica exige cópia estável do questionário |
| RF24 | RF23 | A rodada parte de um modelo |
| RF25 | RF23, RF16 | Cópia é feita na abertura da rodada |

Leitura prática: **RF06 e RF12 são os dois pontos de maior acoplamento**. Mudança neles atinge metade do sistema. **RF25 é pré-requisito silencioso de RF22**: sem congelar o questionário na abertura, o gráfico de evolução compara coisas diferentes e perde o sentido.

## 8 Matriz vertical — requisito sobre artefatos de projeto

Entidades conforme o [MER](../modelagem/modelo-entidade-relacionamento.md) atual (v0.1). "A criar" significa que a entidade **não existe** no MER versionado.

| RF | Entidade | Situação | Tela (Figma) |
|---|---|---|---|
| RF01 | USUARIO | Existe | Login |
| RF02 | USUARIO | Existe | Cadastro de usuários |
| RF03 | TIME | Existe | Cadastro de times |
| RF04 | COMPETENCIA, CARGO, CARGO_COMPETENCIA | **A criar** | Catálogo de competências |
| RF05 | COMPETENCIA_USUARIO | **A criar** | Catálogo de competências |
| RF06 | FEEDBACK (como mensagem) | **A criar** — o `FEEDBACK` atual é resposta a pergunta | Dar feedback |
| RF07 | — | Interface | Dar feedback |
| RF08 | COMENTARIO_FEEDBACK | **A criar** | Detalhe do feedback |
| RF09 | NOTIFICACAO | **A criar** | Painel |
| RF10 | PLANO_ACAO | **A criar** | Dar feedback |
| RF11 | CONVERSA_AGENDADA | **A criar** | Agenda |
| RF12 | PLANO_ACAO, ACAO | **A criar** | Plano de ação |
| RF13 | ACAO | **A criar** | Plano de ação |
| RF14 | CHECK_IN | **A criar** | Plano de ação |
| RF15 | PLANO_ACAO | **A criar** | Plano de ação |
| RF16 | COLETA, COLETA_TIME, COLETA_PARAM | Existe | Criar rodada |
| RF17 | AVALIACAO, FEEDBACK (resposta) | Existe, mas rejeita autoavaliação | Responder rodada |
| RF18 | AVALIACAO | Existe | Acompanhar rodada |
| RF19 | AVALIACAO, FEEDBACK | Existe, sem comparação com autoavaliação | Resultado da rodada |
| RF20 | — | Consulta | Meu desenvolvimento |
| RF21 | — | Consulta | Meu time |
| RF22 | COLETA_PARAM (snapshot) | Existe | Histórico |
| RF23–RF26 | QUESTIONARIO, QUESTIONARIO_ITEM | **A criar** | Catálogo de questionários |

**Treze dos vinte e dois requisitos da lista geral não têm entidade no MER versionado.** É o maior risco da entrega e é o item com responsável definido (Felipe).

## 9 Lacunas identificadas

| ID | Lacuna | Origem | Encaminhamento |
|---|---|---|---|
| LAC01 | Retenção de cerca de 5 anos, inclusive após o desligamento, pedida na entrevista. Nenhum RF trata disso, e o RN12 do IEEE 830 proíbe expurgo, o que é o oposto | FNT02 | Criar RF de retenção e alinhar com RNF02; ver RNF25 da especificação suplementar |
| LAC02 | Avaliação da própria sessão de feedback (emissor avalia a postura do receptor; receptor avalia se agregou valor), pedida com ênfase na entrevista | FNT02 | Está em "fora do escopo" de `requisitos.md`. Se continuar fora, registrar a justificativa com a fonte, não como item solto |
| LAC03 | Direitos do titular na LGPD (consultar e pedir correção dos próprios dados) aparecem só no RNF02, sem RF nem UC | FNT01, FNT02 | Decidir se vira RF ou fica como RNF verificável |
| LAC04 | Peso diferente entre feedbacks e entre indicadores, considerado interessante na entrevista | FNT02 | Manter fora do escopo com justificativa registrada |
| LAC05 | O caso de uso "Registrar feedback informal", na divisão de tarefas do P4, não tem RF próprio: o informal já está dentro de RF06 e UC04 | Divisão do grupo | Ou separa o requisito, ou o P4 detalha o UC04 em conjunto com o Caique |
| LAC06 | "Ciclo de feedback" (divisão), "rodada de avaliação" (lista geral) e "coleta" (IEEE 830 e MER) são o mesmo conceito com três nomes | Interna | Fechar o termo antes das entregas individuais; sugestão: **rodada de avaliação** |
| LAC07 | A numeração RF do IEEE 830 v0.1 colide com a da lista geral, e a rastreabilidade da seção 5 daquele documento aponta para os IDs antigos | Interna | A reescrita do IEEE 830 deve adotar os IDs da lista geral; esta matriz substitui a seção 5 de lá |
| LAC08 | FNT05, FNT06 e FNT07 não existem, então quase toda a origem é uma única entrevista | Interna | Prioridade de cronograma |

## 10 Como manter esta matriz

Requisito novo entra pela lista geral e só depois aqui, com necessidade, caso de uso e critério de verificação preenchidos; requisito sem critério de verificação não é considerado pronto. Requisito alterado obriga a conferir a coluna de dependências da seção 7 e a avisar quem detalha os casos de uso ligados a ele. Requisito removido é riscado com o motivo, não apagado, para preservar o rastro da decisão.
