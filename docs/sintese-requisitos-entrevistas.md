# Síntese dos requisitos das entrevistas

Sistema de feedback e gestão de competências. A disciplina pede a síntese das entrevistas, no plural. Até esta versão existe uma entrevista. Os requisitos abaixo saem somente dela. Nada aqui antecipa a segunda fonte.

Fontes: [roteiro](entrevista-01-roteiro.md) e [transcrição](entrevista-01-transcricao.md). Data da conversa: 20/10/2026. Entrevistada: Adriana Silveira de Souza, Instituto de Informática, mestrado, cliente do domínio. Telefone +55 62 8242-6161. E-mail adriana.silveira@ufg.br. A segunda entrevista está prevista com Nádia Decisão (+55 62 8106-1078 e +55 62 9281-5981) e ainda não foi realizada.

## 1. O que a fonte sabe

A entrevistada descreve o processo de quem ministra feedback, em geral o gestor em relação ao colaborador. Ela distingue avaliação (o julgamento, apoiado em parâmetros e fatos) de feedback (a comunicação desse julgamento). Conhece o processo. Não descreveu telas de um produto de mercado e pediu que o grupo complemente com literatura, outra entrevista e um sistema análogo.

Onde ela disse “eu acho”, “pode ser” ou “seria interessante”, o requisito fica marcado como **desejável**. Onde ela descreveu o que faz e o que o registro precisa ter para o processo existir, o requisito fica marcado como **essencial**.

## 2. Problema

O feedback se perde porque o registro é manual, em papel ou em planilha. O gestor não consegue saber se a pessoa melhorou depois da conversa, nem quais pessoas do time ficaram sem nenhum feedback no período. Sem fato associado, o texto vira opinião. Sem um lugar único, o acompanhamento do plano de ação não se sustenta.

A dor não é a falta de um módulo de salário. É a falta de memória, de indicador observável e de acompanhamento do desenvolvimento.

## 3. Atores

| Ator | Papel no processo |
| --- | --- |
| Gestor | Planeja o ciclo formal, agenda a sessão, registra fatos, dá o feedback, acompanha o plano e abre o 360 do time. É o emissor principal. |
| Colaborador | Recebe o feedback, reflete, constrói o plano junto com o emissor e, no 360, avalia os colegas e a si mesmo. |
| Pares | Dão feedback de igual para igual, dentro do time. A identidade pode ser omitida, se o processo for parametrizado assim. |
| RH | Cadastra as pessoas, pode definir competências e consulta o histórico com identificação de quem avaliou. Não é o emissor típico. |
| Administrador | Pode cumprir o papel de cadastro quando não houver um RH operando o sistema. |

Cargo não concede permissão por si só. A entrevistada separa quem gere o time de quem administra o cadastro e a consulta institucional.

## 4. Processo elicitado

### Informal

1. Ocorre um fato não planejado, a corrigir ou a reconhecer.
2. O emissor registra a data, os fatos, o tipo e o texto na estrutura da categoria.
3. Se for construtivo, emissor e receptor combinam um plano de ação, com pontos de monitoramento e data final.
4. O acompanhamento verifica se houve melhora. Se houve, o ciclo daquele feedback se encerra. Se não houve, pode nascer uma nova ocorrência.

### Formal

1. O gestor planeja o período (exemplo dado: três meses; quatro meses também foi citado).
2. Define se o ciclo é do indivíduo ou da equipe.
3. Estabelece objetivos de comportamento ou de resultado e os indicadores que tornam o objetivo observável.
4. Realiza check-ins no meio do período, coleta fatos e, ao fim, comunica o feedback sobre os parâmetros planejados.
5. O plano de ação e o monitoramento seguem a mesma lógica do informal.

### 360 no time

1. O gestor abre a rodada e convida os participantes do próprio time.
2. Cada pessoa avalia cada membro, inclui a autoavaliação e registra o feedback.
3. O sistema guarda quem não respondeu.
4. A leitura útil compara a autoavaliação com a percepção dos colegas.

A sessão, formal ou informal, pede horário combinado, aviso e lembrete. Depois da sessão construtiva, os dois lados avaliam a própria conversa: o emissor observa se a postura foi colaborativa ou reativa; o receptor observa se o feedback agregou e se o comportamento ou o resultado ficou reconhecível.

## 5. Requisitos funcionais

| ID | Requisito | Força | Evidência na entrevista |
| --- | --- | --- | --- |
| E1-RF01 | Registrar feedback com data, fatos, tipo, texto, emissor e receptor. | Essencial | Abertura do registro. Sem esses dados ela não consegue retomar o feedback. |
| E1-RF02 | Tornar o relato dos fatos obrigatório e ligado ao feedback. | Essencial | “Eu sempre dou feedback em cima de fatos.” Sem fato, o registro fica subjetivo. |
| E1-RF03 | Classificar o feedback como positivo ou construtivo. Não usar a categoria “negativo”. | Essencial | Os dois tipos organizam a conversa. “Negativo” foi recusado por sugerir punição. |
| E1-RF04 | Classificar o feedback como formal ou informal (ad hoc, pontual, não planejado). | Essencial | Os dois modos coexistem. A estrutura de dados pode ser a mesma. |
| E1-RF05 | Ao escolher a categoria, oferecer a estrutura do texto. No positivo: ação ou desempenho, resultados e repercussão para gestor, time e organização. No construtivo: aspecto positivo inicial, fatos, problema, repercussão e plano de ação. | Essencial | Ela descreveu a estrutura como o modo de dar o feedback e aceitou que a escolha da categoria já traga esse molde. |
| E1-RF06 | Registrar plano de ação construído pelo emissor e pelo receptor, com ações, meta, pontos de monitoramento e data final. | Essencial | O plano não é decisão de um lado só. Vale para o construtivo e para o ciclo formal. |
| E1-RF07 | Acompanhar o plano, permitir ajuste das ações e encerrar registrando se houve melhora ou se será aberta nova ocorrência. | Essencial | Ela quer saber quais feedbacks geraram bom resultado. |
| E1-RF08 | Agendar a sessão de feedback e avisar emissor e receptor, com lembrete. | Essencial | Faz parte do planejamento da conversa, distinto do texto do feedback. |
| E1-RF09 | Planejar ciclo formal com periodicidade, escolha entre indivíduo e equipe, objetivos, indicadores e check-ins. | Essencial | Exemplo trabalhado: três meses, verificação no primeiro, segundo e terceiro mês. |
| E1-RF10 | Quebrar competência ampla em aspecto observável e em indicador de fato. Exemplo dado: “comunicação” vira “esclarecer dúvidas com o cliente” e “falar com outros departamentos”, medidos por avaliação do cliente e do setor. | Essencial | Sem o indicador, o objetivo não serve para coletar fato nem para dizer se houve melhora. |
| E1-RF11 | Manter competências fixas por cargo e competências específicas de uma pessoa ou de um grupo, somadas ao conjunto comum. | Essencial | Analista: comunicação e casos de uso para o cargo; modelagem só para uma pessoa. Plano só por cargo existe porque o plano individual consome tempo do gestor. |
| E1-RF12 | Permitir que RH e gestor configurem competências, preservando o gestor como emissor principal do feedback do seu time. | Essencial | “O RH pode fazer. Quem tem mais poder é o gestor.” |
| E1-RF13 | Permitir feedback do gestor a um colaborador de outra área quando um fato dessa pessoa afetou o trabalho do gestor. O caso comum continua sendo o subordinado direto. | Desejável | Exemplo do design não entregue. Ela tratou como possibilidade, não como regra do dia a dia. |
| E1-RF14 | Reutilizar parâmetros entre ciclos e manter formulário já pronto do RH, com metas extras por indivíduo. | Essencial | Ela confirmou a persistência da lista e o uso de um formulário prévio mais acréscimos. |
| E1-RF15 | Consultar um feedback específico e a evolução de um mesmo indicador ao longo do tempo. | Essencial | Os dois recortes foram pedidos. O gerente citado por ela já faz a série em planilha. |
| E1-RF16 | Mostrar, para o gestor, quais pessoas do time receberam feedback num período (exemplo: seis meses) e quais não receberam. | Essencial | Visão gerencial citada como motivo para centralizar. |
| E1-RF17 | Operar com os perfis gestor, colaborador e RH. Um administrador pode cadastrar pessoas. | Essencial | RH entra pelo controle institucional do histórico. |
| E1-RF18 | O receptor consulta os próprios feedbacks. O RH consulta o histórico identificando o emissor. O gestor da sessão também identifica emissor e receptor. | Essencial | Resposta direta sobre LGPD e acesso. |
| E1-RF19 | No feedback de gestor, exibir quem falou. Entre pares, permitir ocultar o emissor. A visibilidade é parâmetro do processo, não uma regra única. | Essencial | Anonimato total foi recusado para o chefe–colaborador. Para pares, a omissão ficou em aberto como parametrização. |
| E1-RF20 | Conduzir as modalidades: gestor para colaborador; os dois sentidos; pares; 360 do time com autoavaliação, inclusive colaborador avaliando o gestor. | Essencial | “No 360, a gente avalia todo mundo.” Autoavaliação entrou no mesmo movimento. |
| E1-RF21 | No 360, o gestor abre a rodada, convida o time e cada participante avalia cada membro. O alcance padrão é o próprio time. | Essencial | “O feedback é só para o meu time.” Todos com todos, não o time inteiro sobre uma única pessoa. |
| E1-RF22 | Comparar a autoavaliação com a percepção dos colegas e mostrar alinhamento ou divergência. | Essencial | Ela chamou essa comparação de informação interessante e a ligou ao 360. |
| E1-RF23 | Registrar quem foi convidado e não respondeu, sem aplicar punição no sistema. | Essencial | A ausência importa. A consequência disciplinar ficou fora. |
| E1-RF24 | Depois da sessão, registrar a avaliação do processo: postura do receptor (colaborativa ou reativa) e percepção do receptor sobre o valor do feedback. | Essencial | Serve para saber se o processo de feedback está funcionando. |
| E1-RF25 | Aceitar texto estruturado e, além dele, escala ordinal ou numérica, com níveis intermediários. Atingiu ou não atingiu não esgota a avaliação. | Desejável | Ela autorizou incrementar a estrutura com escala. Não fixou valores (0 a 5, 0 a 10 ou Likert). |
| E1-RF26 | Atribuir pesos diferentes a indicadores de um mesmo feedback e a feedbacks de momentos diferentes. | Desejável | “Pode ser interessante.” Não houve regra de cálculo. |
| E1-RF27 | Cadastrar as pessoas de uma organização pelo RH ou por um administrador, por importação de planilha ou por inclusão manual. | Essencial | Importar é preferível. Sem importação, o cadastro manual resolve. |
| E1-RF28 | Impedir a exclusão de feedback já registrado. O registro integra o histórico oficial. | Essencial | “Apagar não.” Mal-entendido se resolve na sessão, não apagando o fato. |
| E1-RF29 | Atender uma organização por implantação. O mesmo produto pode ser oferecido a outras organizações, cada uma na sua base. | Essencial | Base única com várias empresas foi recusada. Intranet da organização foi o cenário aceito. |

## 6. Regras de negócio

| ID | Regra |
| --- | --- |
| E1-RN01 | Todo feedback se apoia em fato observável de comportamento ou de resultado. Opinião sobre personalidade não é feedback válido. |
| E1-RN02 | O indicador e o que será avaliado são definidos e comunicados antes do ciclo formal. As pessoas prestam contas disso, não de um critério revelado só no fim. |
| E1-RN03 | Positivo reconhece ação, resultado e repercussão. Construtivo começa por um aspecto positivo, apresenta o problema e termina em plano. |
| E1-RN04 | O plano de ação é acordo dos dois. O emissor conduz a reflexão; não entrega a ação pronta como ordem unilateral. |
| E1-RN05 | Formal tem data e periodicidade. Informal nasce do evento e não depende de calendário. |
| E1-RN06 | Competência ampla não entra sozinha. Ela precisa de aspecto e de fonte de fato. |
| E1-RN07 | No 360, o desenho preferido é todos avaliam todos no próprio time, com autoavaliação. Avaliar só uma pessoa, poupando os demais, foi visto como risco de animosidade. A entrevistada não quis proibir outros desenhos: o gestor escolhe. |
| E1-RN08 | Identidade do emissor é conhecida no feedback do gestor. Ocultar o par é uma opção a parametrizar, não o padrão desse fluxo. |
| E1-RN09 | Feedback enviado não é apagado. Correção de entendimento ocorre na conversa e no plano, e fica registrada. |
| E1-RN10 | Não responder fica registrado. Punição, retaliação e desligamento não são funções do sistema. O histórico pode, fora dele, subsidiar uma decisão de RH. |
| E1-RN11 | Promoção e salário não são calculados aqui. Um histórico consistente de feedbacks positivos pode ser consultado por quem decide isso em outro sistema. |
| E1-RN12 | Denúncia, assédio e canal de ouvidoria não são tipos de feedback deste produto. Falha grave de desempenho continua sendo feedback, com fatos e oportunidade de desenvolvimento. |

## 7. Requisitos não funcionais e de processo

| ID | Requisito | Força |
| --- | --- | --- |
| E1-RNF01 | Tratar dados pessoais conforme a LGPD. O acesso à identidade de quem avaliou é restrito aos papéis autorizados: RH, gestor da sessão e receptor, com a ressalva de parametrização entre pares. | Essencial |
| E1-RNF02 | Manter o histórico enquanto a pessoa estiver na organização. Depois da saída, a sugestão da entrevistada foi conservar por cerca de cinco anos. Não houve norma jurídica citada. | Desejável |
| E1-RNF03 | Centralizar o que hoje está em papel e em Excel, de forma que registrar fato, plano e consulta não exija reconstruir o histórico de cabeça. | Essencial |
| E1-RNF04 | Usar a mesma estrutura de registro para feedback presencial e remoto. | Essencial |
| E1-RNF05 | Ao implantar o processo na organização, haver treinamento sobre o que é feedback, para reduzir a leitura do convite como punição. A entrevistada descreveu isso como prática de implantação, não como módulo obrigatório do software. | Processo |

Ela também separou sistema sociotécnico de software: pessoas grosseiras ou uma cultura que trata feedback como ataque fazem o processo falhar mesmo com ferramenta boa. Isso não vira tela. Explica por que a estrutura do texto, o fato obrigatório e a avaliação da sessão existem.

## 8. Fora de escopo, dito pela entrevistada

| ID | Não entra neste sistema |
| --- | --- |
| E1-FE01 | Cálculo ou decisão de salário, promoção ou desligamento. |
| E1-FE02 | Punição de quem não respondeu. |
| E1-FE03 | Canal de denúncia, reclamação ou mediação por terceiro externo. |
| E1-FE04 | Várias empresas compartilhando a mesma base de pessoas e feedbacks. |
| E1-FE05 | Garantir, pelo software, que o emissor seja educado. A ferramenta apoia o rito; a postura é do processo humano. |

Para a etapa seguinte do trabalho, ela aceitou que a arquitetura e o design implementem um recorte menor do que a especificação de requisitos. O exemplo dado foi ficar só em gestor e colaborador. Os requisitos desta síntese permanecem no mapa amplo. O recorte de implementação é decisão posterior do grupo.

## 9. Lacunas que a segunda entrevista precisa fechar

A primeira fonte é Adriana Silveira de Souza, especialista do processo, em conversa de aula. A próxima entrevista está marcada com Nádia Decisão (+55 62 8106-1078 e +55 62 9281-5981). Faltam, nessa segunda fonte, quem recebe feedback no trabalho e quem opera o rito em RH ou gestão, no manual ou numa ferramenta.

Pontos ainda sem resposta fechada:

1. Valores concretos da escala: Likert, 0 a 5, 0 a 10 ou outro intervalo.
2. Se o texto pode ser editado antes do fim da sessão ou se, uma vez gravado, também não muda. Ficou fechado apenas que não se apaga.
3. Como o peso altera média, evolução e comparação. A ideia foi aceita sem fórmula.
4. Qual é o padrão de anonimato entre pares e se o receptor do par vê o nome depois que a rodada fecha.
5. Se o 360 de uma única pessoa, excepcional, entra no produto ou se o grupo segue só o todos-com-todos.
6. Se a participação obrigatória é regra da organização configurável ou apenas um registro de ausência.
7. Canal do lembrete: dentro do sistema, e-mail ou ambos.
8. Quem confirma o plano de ação quando emissor e receptor discordam.
9. Prazo de retenção: a fala foi “a princípio não descartar” e, em seguida, “talvez cinco anos”. Não é política fechada.
10. Quais campos do formulário pronto do RH são fixos e quais o gestor pode acrescentar no meio de um ciclo já aberto.
11. Se a avaliação da sessão (postura e valor percebido) é visível para o RH ou só para quem participou da conversa.

Perfis sugeridos por ela para a próxima entrevista: pessoa de RH ou gestor que ministre feedback, inclusive quem faça isso em planilha. Entrevistado do próprio grupo serve se o relato trouxer fato do trabalho, não só opinião genérica.

## 10. Relação com a especificação já escrita

A [especificação IEEE 830](especificacao-requisitos-ieee830.md) e o [domínio](dominio.md) foram escritos antes desta transcrição e tratam 360, autoavaliação, plano de ação, metas e anonimato como extensões ou pendências. A entrevista puxa esses temas para o processo principal.

Convergências que a entrevista reforça:

- Fato e indicador no lugar de texto puramente subjetivo.
- Histórico preservado, sem exclusão do feedback enviado.
- Gestor, profissional e RH como papéis diferentes.
- Questionário com parâmetros reutilizáveis e leitura da evolução.
- Uma organização, com cadastro de pessoas.
- Foco em desenvolvimento, não em folha de pagamento.

Tensões para o grupo decidir, sem que esta síntese reescreva a especificação:

| Tema | Entrevista 1 | Documentação anterior |
| --- | --- | --- |
| Autoavaliação | Entra no 360. | O núcleo documentado não tem autoavaliação. |
| 360 e pares | Fazem parte do processo descrito. 360 é todos com todos no time. | Tratados como extensão. |
| Plano, meta e check-in | São o acompanhamento que justifica o sistema. | Tratados como extensão. |
| Anonimato | Gestor é identificado. Par pode omitir o emissor. RH vê a identidade. | Reciprocidade com identidade conhecida; anonimato não fechado. |
| Escala | Ordinal ou numérica, com nível intermediário; texto estruturado. Pesos são desejáveis. | Escalas 0–10, 0–5 e booleano, sem peso. |
| Edição | Exclusão recusada. Edição não foi autorizada. | Respostas enviadas ficam imutáveis; rascunho ainda pode mudar. |

Enquanto a segunda entrevista não ocorrer, estes identificadores `E1-*` são a rastreabilidade da primeira fonte. Eles ainda não substituem os `RF` da especificação.
