# Sistemas análogos de feedback: pesquisa e visão

## Contexto e objetivo

Este documento apoia a decisão sobre o que construir no nosso sistema de feedback, comparando-o com sistemas análogos do mercado. Serve de insumo para a ERS (IEEE 830, v0.1) já em elaboração.

Foram levantadas cinco ferramentas como alternativas atuais: Qualtrics, SurveyMonkey, Typeform, Lark e Hotjar. Nem todas são comparáveis. O núcleo do nosso sistema é a avaliação mútua entre pessoas — cada par gera dois sentidos (A sobre B e B sobre A), por seleção de pares ou de times, com análise individual ao longo do tempo. Isso o coloca na categoria de feedback 360° / gestão de desempenho, e não na de pesquisas genéricas ou análise de uso de site.

O documento faz três coisas: seleciona os análogos relevantes e justifica a escolha; sintetiza as funcionalidades de cada um e cruza com os nossos requisitos; e consolida um Documento Visão e o caso de uso "Consultar análise e evolução do colaborador". O foco é apoiar decisões e insights, não esgotar cada produto.

## Sistemas selecionados e critério

Mantemos o Qualtrics e acrescentamos quatro concorrentes diretos de feedback de pessoas: Lattice, Culture Amp, 15Five e Microsoft Viva Glint. Lark, Hotjar, SurveyMonkey e Typeform saem como análogos do núcleo.

O critério é a aderência ao núcleo: avaliação multi-fonte de pessoas (360°), com ciclos, papéis de avaliador/avaliado e análise de resultados. Ferramentas de formulário genérico coletam respostas, mas não modelam avaliação recíproca entre participantes nem evolução individual.

| Ferramenta | Categoria | Entra como análogo? | Por quê |
| --- | --- | --- | --- |
| Qualtrics | Pesquisa/XM + módulo 360 | Sim | Módulo 360 multi-rater dedicado dentro da suíte |
| Lattice | Gestão de desempenho | Sim | 360, peer review e analytics integrados a reviews/OKRs |
| Culture Amp | Engajamento + desempenho | Sim | 180°/360° com auto, pares, upward e gestor |
| 15Five | Gestão contínua de desempenho | Sim | Check-ins contínuos + reviews + 360 |
| Viva Glint | Engajamento + 360 (desenvolvimento) | Sim | 360 multi-rater focado em desenvolvimento |
| SurveyMonkey | Pesquisas gerais | Parcial | Faz questionários, mas não avaliação recíproca por time |
| Typeform | Formulários conversacionais | Parcial | Serve só como referência de UX de preenchimento |
| Lark | Suíte de colaboração | Não | Não é sistema de feedback |
| Hotjar | Análise de comportamento em site | Não | Analisa uso de site, não avalia pessoas |

## Pesquisa dos sistemas análogos (funcionalidades)

Os cinco convergem num mesmo padrão: feedback 360 multi-fonte, organizado em ciclos, com questionário configurável, relatório por avaliado e analytics. Diferem no foco — de pesquisa enterprise (Qualtrics) a cadência contínua (15Five) e desenvolvimento puro (Viva Glint).

### [Qualtrics 360](https://www.qualtrics.com/au/qualtrics-360)

- Módulo 360 dentro da suíte de Employee Experience; coleta multi-fonte (gestor, pares, subordinados, clientes) com anonimato e relatórios individualizados.
- Automação do ciclo via integração com HRIS (Workday, SAP SuccessFactors), com convites e lembretes automáticos.
- Relatórios por avaliado que agregam o feedback e ligam a competências e planos de desenvolvimento.
- Forte em analytics e benchmarking; posicionamento enterprise.

### [Lattice](https://lattice.com/lp/360-reviews)

- Plataforma de gestão de desempenho; ciclos de 360 com auto, pares, subordinados e gestor.
- Nomeação de pares pelo avaliado com aprovação do gestor (ou o gestor nomeia).
- Templates de perguntas, relatórios e analytics; integra reviews, 1:1s, OKRs e feedback contínuo.
- Posicionada para mid-market, "tudo em um".

### [Culture Amp](https://www.cultureamp.com/platform/perform/360-degree-feedback-tool)

- Combina engajamento e desempenho; suporta 180° e 360° dentro dos ciclos de review.
- Um ciclo reúne auto, pares, upward e gestor, com etapas de nomeação.
- Feedback contínuo ao longo do ano alimenta a review; benchmarking por demografia/indústria.
- Relatórios orientados à ação/desenvolvimento.

### [15Five](https://www.capterra.com/p/140437/15Five/)

- Gestão contínua de desempenho baseada em check-ins semanais, feedback informal e reconhecimento ("High Fives").
- Reviews e 360 disponíveis, além de OKRs e Talent Matrix.
- Forte na cadência contínua e em tendências; menos na avaliação formal estruturada.
- Mid-market; sem HRIS/folha embutidos.

### [Microsoft Viva Glint](https://learn.microsoft.com/en-us/viva/glint/setup/360-overview)

- Programa 360 dentro do Viva Glint, explicitamente para desenvolvimento, não avaliação de desempenho.
- O avaliado faz auto-avaliação e seleciona os provedores de feedback (gestor, subordinados, colaboradores).
- Organizado em programas/ciclos; relatório enviado ao avaliado após o fechamento do ciclo; confidencialidade com limiar mínimo de respostas.
- Integrado ao ecossistema Microsoft/Viva.

### Matriz comparativa

Linhas = dimensões que o mercado trata de forma comum; as dimensões específicas do nosso sistema vão para a síntese abaixo.

| Dimensão | Qualtrics | Lattice | Culture Amp | 15Five | Viva Glint |
| --- | --- | --- | --- | --- | --- |
| Feedback 360 multi-fonte | Sim | Sim | Sim | Sim | Sim |
| Nomeação de avaliadores com aprovação | Parcial | Sim | Sim | Parcial | Sim |
| Perguntas/competências configuráveis | Sim | Sim | Sim | Sim | Sim |
| Questionário fixado por ciclo | Sim | Sim | Sim | Sim | Sim |
| Papéis e permissões por escopo | Sim | Sim | Sim | Sim | Sim |
| Anonimato/confidencialidade com limiar | Sim | Sim | Sim | Parcial | Sim |
| Relatório liberado ao encerrar o ciclo | Sim | Sim | Sim | Parcial | Sim |
| Analytics e tendência ao longo do tempo | Sim | Sim | Sim | Sim | Sim |
| Planos de ação/desenvolvimento | Sim | Sim | Sim | Sim | Sim |

Marcações baseadas em material público dos fornecedores e de sites de comparação (G2, Capterra, Gartner), não em teste prático. "Parcial" = disponível com limitações ou dependente de configuração.

## Síntese dos requisitos do sistema análogo

O mercado converge num padrão de feedback 360 por ciclos. Nosso sistema compartilha essa base, mas diverge em pontos que nenhum dos cinco trata como conceito de primeira classe. Daí sai o que vale copiar e o que é diferencial nosso.

**Padrões a adotar (confirmados pelo mercado):**

- Ciclos com questionário fixado: todos congelam o instrumento por ciclo — reforça o nosso RF09/RN05.
- Papéis e permissões por escopo, com confidencialidade e limiar mínimo de respostas — alinhado a RF01/RNF01 e à decisão PV04.
- Relatório liberado só após o fechamento do ciclo — alinhado ao nosso RN09.
- Analytics com tendência/evolução e relatório por avaliado — é o coração do nosso RF15.

**Onde o nosso spec diverge ou avança:**

- Avaliação recíproca por par (dois sentidos independentes A↔B): o mercado é centrado no avaliado (vários avaliadores sobre um sujeito), não em pares simétricos. Nosso modelo de par com dois sentidos e regras de reciprocidade (RN01) é distintivo.
- Geração automática por time: selecionar um time e gerar todas as combinações internas (n×(n−1) avaliações) sem vínculo individual prévio não aparece nos análogos, que usam nomeação individual de avaliadores. É diferencial e também risco de volume — validar a meta de carga (RNF04).
- Mistura de escalas numéricas (0–10, 0–5) e booleano por pergunta, com análise que nunca combina os dois numa média única (RN10): os análogos usam competências em escala; o tratamento booleano separado é decisão nossa.
- Preservação sem exclusão física (desativação/cancelamento) como regra transversal (RN12): é prática de engenharia, não um recurso que os fornecedores anunciam; manter como requisito interno.

**Decisões que a pesquisa reforça:**

- Anonimato: o mercado protege o avaliador com limiar mínimo de respostas. Nosso modelo de par de duas pessoas torna o anonimato inviável (PV04) — assumir identificação, como já proposto.
- Não perseguir o escopo enterprise (HRIS, benchmarking, LMS, planos de desenvolvimento) no núcleo; são as extensões da seção 4.2 da ERS.

## Documento Visão

Visão enxuta do produto, alinhada à ERS.

**Problema.** As avaliações tradicionais dão uma visão única (só o gestor) e perdem histórico comparável. Falta uma forma estruturada de feedback mútuo entre pares e dentro de times, com análise individual ao longo do tempo.

**Oportunidade.** Entregar um sistema focado em avaliação recíproca por pares e times, com análise de evolução, sem a complexidade e o custo das suítes enterprise.

**Declaração de posição.** Para o RH e os gestores que precisam coletar e analisar feedback mútuo entre colaboradores, o sistema de feedback é uma aplicação web de avaliação 360 por pares e times que gera avaliações recíprocas, preserva o histórico e analisa a evolução. Diferente de ferramentas de pesquisa genérica e de suítes enterprise, o nosso modela pares e times com reciprocidade e foca no núcleo, sem depender de HRIS.

**Stakeholders e público.** RH (administra), Gestor (acompanha o seu time), Profissional/PROF (avalia e consulta os próprios resultados), e os avaliadores acadêmicos do contexto do trabalho.

**Principais recursos.** Cadastro de usuários, times, grupos e parâmetros; configuração de coleta por pares ou por times; geração automática dos dois sentidos; preenchimento com escalas e booleano; liberação condicionada dos resultados; análise e evolução por usuário; auditoria de alterações.

**Premissas e restrições.** Aplicação web sobre banco relacional (proposta); um perfil por conta; sem exclusão física de dados; HTTPS em produção; sem integração externa obrigatória no núcleo.

**Escopo (núcleo).** Avaliação mútua por pares e times, ciclos com questionário congelado, e análise histórica por usuário.

**Fora de escopo (extensões a validar).** Feedback 360 chefe-colaborador completo, anonimato, planos de ação, metas de desenvolvimento e as classificações formal/informal citadas no enunciado.

## Caso de uso: Consultar análise e evolução do colaborador

**Identificador.** UC-15 (realiza RF14 e RF15).

**Ator principal.** PROF, que consulta os próprios resultados liberados. **Atores secundários.** RH e Gestor, que consultam dentro do seu escopo, sujeito à matriz de acesso (PV04).

**Pré-condições.** Usuário autenticado e ativo; existe ao menos uma coleta encerrada com avaliações válidas liberadas para o alvo; permissões conforme o perfil.

**Pós-condição de sucesso.** O sistema exibe os indicadores agregados e a evolução entre coletas comparáveis, sem expor rascunhos de terceiros nem pares incompletos ou cancelados.

**Fluxo principal:**

1. O usuário acessa a área de histórico e análise.
2. Seleciona o colaborador alvo (o PROF vê a si mesmo; RH e Gestor veem os do seu escopo).
3. Define os filtros: período de encerramento, coleta, grupo e parâmetro.
4. O sistema valida as permissões sobre o alvo e o recorte.
5. O sistema reúne as respostas válidas e ativas das coletas encerradas no recorte.
6. Calcula os indicadores: média normalizada para escalas; contagem e proporção de Sim/Não para booleanos, separados da média numérica (RN10).
7. Monta a evolução entre coletas, separando as versões de pergunta ou escala que não são comparáveis (RN11).
8. Apresenta os resultados por coleta, grupo e parâmetro; recortes sem respostas válidas aparecem como "sem dados".

**Fluxos alternativos e exceções:**

- A1 — Recorte sem dados: exibe "sem dados", sem erro.
- A2 — Versões incomparáveis: separa as séries e sinaliza a mudança de pergunta, escala ou composição do grupo (RN11).
- E1 — Sem permissão sobre o alvo: acesso negado, inclusive por acesso direto ao ID do registro (RNF01, CA02).
- E2 — Par incompleto ou cancelado: fica fora dos resultados recebidos e da análise (RN09); o autor mantém acesso ao próprio envio.
- E3 — Resultado ainda não liberado (coleta não encerrada ou falta um dos sentidos): não exibe o conteúdo recebido (RN09, CA09).

**Regras de negócio associadas.** RF14, RF15, RN09, RN10, RN11.

**Critérios de aceitação ligados.** CA09 (liberação), CA10 (cálculo) e CA11 (histórico e comparabilidade).
