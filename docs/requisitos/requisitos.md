# Lista Geral de Requisitos

Sistema web de feedback e desenvolvimento de competências.

Versão 0.3, 17/11/2026 (versão leve: só o mínimo que resolve o problema, com poucos passos). Responsável: Caique Duarte. Situação: aguardando validação do grupo.

## 1 Visão rápida

O sistema serve para **registrar, dar e acompanhar feedbacks baseados em fatos**, para que o gestor saiba se o colaborador realmente melhorou depois do feedback. Hoje isso fica em papel, Excel ou na cabeça do gestor e se perde (dor principal citada na entrevista).

O roteiro que o sistema apoia é o descrito pela professora:

> **coletar fatos → dar o feedback → combinar um plano de ação → acompanhar com check-ins → encerrar**

Princípio de projeto: **pouca burocracia**. Dar um feedback cabe em uma tela só. O que não for essencial para resolver o problema ficou fora.

O foco é o **desenvolvimento da pessoa**. Promoção, salário e punições ficam fora do escopo (são de outros sistemas de RH).

### Como os tipos de feedback aparecem no sistema

| Tipo (enunciado/entrevista) | Como funciona aqui |
|---|---|
| Positivo / construtivo | Escolhido no formulário do feedback |
| Informal | Feedback avulso, dado a qualquer momento (RF06) |
| Formal | Rodada de avaliação com prazo (RF15) e/ou plano de ação com objetivo, check-ins e data final (RF12) |
| Chefe → colaborador | Feedback do gestor para alguém do time |
| Pares / 360 | Rodada de avaliação do time: todos avaliam todos, com autoavaliação |

## 2 Fontes

| Fonte | O que trouxe |
|---|---|
| Enunciado do projeto (PDF da disciplina) | Tipos de feedback (chefe-colaborador, pares, 360), formal/informal/positivo/construtivo, questionários, análise com gráficos, anonimato, plano de ação, metas, LGPD, plataforma web |
| Entrevista com a professora (transcrição) | Feedback sempre com fatos ("campo obrigatório"); estrutura do positivo e do construtivo; plano de ação feito em conjunto, com check-ins e encerramento; agendar a sessão com lembrete; objetivos com indicadores; competências fixas por cargo + específicas; perfis gestor/colaborador/RH; não excluir feedback; 360 dentro do time com autoavaliação comparada; anonimato opcional entre pares; registrar quem não respondeu; visão do time nos últimos 6 meses; evolução ao longo do tempo |
| Anotações do Caique na entrevista | Fato ("a Júlia é pontual"); chefe → colaborador e gestor → colaboradores; positivo ou construtivo, formal e informal; controle do tipo de feedback e acompanhamento; indicadores ("melhorar comunicação em que aspecto?"); competências fixas e não fixas; 360 com autoavaliação; "meu time" |
| Ferramentas de mercado | Referência geral, ver seção 8 |

Decisões do grupo (não vieram das fontes): escala de 1 a 5 na rodada de avaliação; feedback não é editável, só comentável; notificações apenas dentro da plataforma.

## 3 Perfis (atores)

| Perfil | Quem é | O que faz no sistema |
|---|---|---|
| **Colaborador** | Qualquer funcionário | Dá e recebe feedback, comenta, responde rodadas de avaliação (com autoavaliação), edita e faz check-in no seu plano de ação, vê seu desenvolvimento |
| **Gestor** | Líder de um time (também é colaborador) | Tudo do colaborador + agenda conversas, cria planos de ação, conduz rodadas de avaliação, acompanha o painel "Meu time" |
| **RH** | Área de pessoas | Cadastra usuários, times e competências; consulta o histórico de feedbacks da empresa |

## 4 Requisitos funcionais

### 4.1 Cadastros

| ID | Requisito |
|---|---|
| RF01 | O sistema deve permitir login, liberando as telas de acordo com o perfil (Colaborador, Gestor, RH). |
| RF02 | O RH deve cadastrar, editar e desativar usuários (nome, e-mail, cargo, time, perfil). Usuário não é excluído, só desativado. |
| RF03 | O RH deve cadastrar times e definir o gestor de cada time. |
| RF04 | O RH deve manter a lista de competências e indicar quais competências são fixas de cada cargo. |
| RF05 | O gestor deve poder adicionar uma competência específica a um colaborador, além das do cargo (ex.: "a Isadora precisa melhorar modelagem"). |

### 4.2 Feedback

| ID | Requisito |
|---|---|
| RF06 | O usuário deve dar um feedback em **uma única tela**, informando: receptor, tipo (**positivo** ou **construtivo**), **fato** (texto, obrigatório), feedback (texto) e competência (opcional). Data e emissor são preenchidos automaticamente. |
| RF07 | Conforme o tipo escolhido, o campo de feedback deve mostrar uma **dica do roteiro** (não obrigatório). Positivo: o que a pessoa fez, o resultado e o impacto para o gestor, o time e a organização. Construtivo: um ponto positivo, o fato, o impacto e a pergunta "o que pode ser feito para não acontecer de novo?". |
| RF08 | O feedback **não pode ser excluído nem editado** depois de enviado. Emissor e receptor podem adicionar comentários a ele. |
| RF09 | O receptor deve ser notificado e ver o feedback no seu painel. |
| RF10 | Ao enviar um feedback construtivo, o sistema deve oferecer o botão **"Criar plano de ação"** já ligado a ele. |
| RF11 | O gestor pode, opcionalmente, **agendar uma conversa de feedback** (data, hora e participante); o sistema lembra os dois antes da conversa. |

### 4.3 Plano de ação

| ID | Requisito |
|---|---|
| RF12 | O gestor deve criar um **plano de ação** com: objetivo (pode incluir o indicador em texto, ex.: "nota do cliente acima de 4"), lista de ações, data final e datas de check-in. O plano pode nascer de um feedback construtivo, de uma rodada de avaliação ou ser criado direto. |
| RF13 | O colaborador também pode **editar as ações** do plano, para que ele seja construído pelos dois. |
| RF14 | Em cada check-in, gestor ou colaborador registra um **comentário rápido** sobre o andamento. O sistema lembra os dois na data do check-in. |
| RF15 | Na data final, o gestor **encerra o plano** marcando **"melhorou"** ou **"não melhorou"**. Se não melhorou, o sistema sugere dar um novo feedback. |

### 4.4 Rodada de avaliação (formal, pares e 360)

| ID | Requisito |
|---|---|
| RF16 | O gestor deve criar uma **rodada de avaliação** escolhendo: participantes do time, competências avaliadas, prazo e se as respostas entre pares ficam **anônimas** ou não. |
| RF17 | Cada participante avalia os outros participantes **e a si mesmo**: nota de 1 a 5 por competência e um comentário com fatos. |
| RF18 | O gestor deve ver **quem já respondeu e quem não respondeu**. |
| RF19 | Ao fim do prazo, o sistema mostra o resultado de cada pessoa, **comparando a autoavaliação com a média dos outros**. A partir do resultado, o gestor pode dar um feedback ou criar um plano de ação. |

### 4.5 Acompanhamento

| ID | Requisito |
|---|---|
| RF20 | O colaborador deve ter a tela **"Meu desenvolvimento"**: feedbacks recebidos, planos de ação, resultados das rodadas e próximas datas. |
| RF21 | O gestor deve ter o painel **"Meu time"**: quem recebeu feedback nos últimos 6 meses (e quem não recebeu), planos ativos e atrasados, rodadas em andamento. |
| RF22 | O sistema deve mostrar o **histórico de feedbacks** de um colaborador, com filtro por período, tipo e competência, e um **gráfico de evolução** das notas por competência entre as rodadas. O gestor vê o do seu time e o RH vê o de toda a empresa. |

## 5 Regras de negócio

| ID | Regra |
|---|---|
| RN01 | Todo feedback precisa de um fato. Feedback é sobre comportamento ou resultado, nunca sobre personalidade. |
| RN02 | Feedback não é excluído nem editado; ajustes são feitos por comentário. |
| RN03 | O gestor é sempre identificado. Anonimato só pode ser ligado para respostas entre pares numa rodada de avaliação. |
| RN04 | Quem vê o quê: o receptor vê o que recebeu; o emissor vê o que deu; o gestor vê o do seu time; o RH vê tudo. |
| RN05 | A rodada de avaliação é limitada aos participantes do time escolhidos pelo gestor. |
| RN06 | Não responder uma rodada fica registrado; o sistema não aplica nenhuma consequência. |

## 6 Requisitos não funcionais

| ID | Requisito |
|---|---|
| RNF01 | **Plataforma:** aplicação web responsiva, utilizável no computador e no celular pelo navegador. |
| RNF02 | **LGPD:** coletar só os dados necessários, informar ao usuário para que são usados, permitir que ele consulte e peça correção dos seus dados pessoais e restringir o acesso conforme RN04. |
| RNF03 | **Segurança:** acesso só com login, senha armazenada de forma criptografada e comunicação via HTTPS. |
| RNF04 | **Rastreabilidade:** guardar quem criou cada feedback, comentário e plano, e quando. |
| RNF05 | **Usabilidade:** dar um feedback em uma tela só, com linguagem simples, em português do Brasil. |
| RNF06 | **Acessibilidade:** campos com rótulos, contraste adequado e navegação por teclado. |

## 7 Fora do escopo

- Decisão de promoção, salário, bônus ou punição (o histórico pode apoiar o RH, mas a decisão é fora do sistema).
- Folha de pagamento, ponto e treinamentos.
- App mobile nativo.
- Funções "bom ter" que deixamos de fora para manter o sistema leve: solicitar feedback, avaliar a conversa de feedback, cadastro separado de fatos e de indicadores, modelos de questionário, relatórios e exportação para o RH, notificação por e-mail.

## 8 Ferramentas de mercado (referência geral)

> **Atenção:** esta tabela é uma **referência geral**, baseada em conhecimento público sobre essas ferramentas. **Os recursos não foram conferidos nas páginas oficiais** durante este levantamento. A pesquisa detalhada de sistema análogo é outra parte do trabalho e deve confirmar estas informações.

| Ferramenta | Recursos que costuma oferecer (não verificado) | Site |
|---|---|---|
| Lark | Avaliações de desempenho e modelos de avaliação 360 | larksuite.com |
| Lattice | Feedback, reuniões 1:1, metas e ciclos de avaliação | lattice.com |
| 15Five | Check-ins periódicos, reconhecimento entre colegas, 1:1 | 15five.com |
| Culture Amp | Avaliação 360 e planos de desenvolvimento | cultureamp.com |
| Leapsome | Feedback, competências por cargo, avaliações | leapsome.com |
| Qulture.Rocks (BR) | Feedback, 1:1, PDI, avaliação de desempenho | qulture.rocks |
| Feedz (BR) | Feedbacks e elogios, 1:1, PDI, pesquisa de clima | feedz.com.br |

Os requisitos deste documento vieram da **entrevista, das anotações e do enunciado** (seção 2). As ferramentas só servem para mostrar que ideias como check-in, 360 com autoavaliação e competências por cargo são comuns no mercado.

## 9 Casos de uso

Os diagramas estão em [`casos-de-uso.drawio`](../casos-de-uso/casos-de-uso.drawio) (abrir em [app.diagrams.net](https://app.diagrams.net) ou na extensão Draw.io do VS Code). O arquivo tem duas páginas: **Visão geral** e **UC07 Plano de ação** (detalhado).

| UC | Nome | Atores | Requisitos |
|---|---|---|---|
| UC01 | Fazer login | Todos | RF01 |
| UC02 | Manter usuários e times | RH | RF02, RF03 |
| UC03 | Manter competências | RH, Gestor | RF04, RF05 |
| UC04 | Dar feedback | Colaborador, Gestor | RF06–RF10 |
| UC05 | Consultar "Meu desenvolvimento" | Colaborador | RF08, RF09, RF20 |
| UC06 | Agendar conversa de feedback | Gestor | RF11 |
| UC07 | Gerenciar plano de ação | Gestor, Colaborador | RF12–RF15 |
| UC08 | Conduzir rodada de avaliação | Gestor | RF16, RF18, RF19 |
| UC09 | Responder rodada de avaliação | Colaborador, Gestor | RF17 |
| UC10 | Consultar painel "Meu time" | Gestor | RF21 |
| UC11 | Consultar histórico de feedbacks | Gestor, RH | RF22 |

O Gestor herda todos os casos de uso do Colaborador. As notificações na plataforma aparecem no diagrama como `<<include>>` "Notificar participantes" em UC04, UC06, UC07 e UC08.

## 10 Pontos para validar com o grupo

1. O IEEE 830 do Felipe trata a avaliação como "coletas" configuradas pelo RH. Aqui a rodada de avaliação é criada pelo **gestor** (como a professora descreveu). Precisamos alinhar quem cria.
2. Com o anonimato ligado, o RH pode ver quem respondeu? A professora disse que o RH tem acesso a esses dados, mas isso enfraquece o anonimato. Decidir antes do protótipo.
