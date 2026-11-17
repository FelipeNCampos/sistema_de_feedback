# Síntese dos requisitos dos questionários

Sistema web de feedback e desenvolvimento de competências.

Versão 0.1, 17/11/2026. Responsável: Gabriel Mendes (P4). Fonte: [questionários aplicados](questionarios.md) (Q1: Mariana Lopes, gestora; Q2: Rafael Souza, colaborador). Os IDs seguem a [Lista Geral de Requisitos](requisitos.md).

## 1 Resumo

Os dois questionários confirmam a dor principal da entrevista: **o feedback não fica registrado e se perde**. Na prática, os feedbacks informais acontecem "no corredor" e não são anotados (Q1), ou nem chegam a acontecer (Q2). Quando há feedback construtivo, as ações são combinadas de boca e ninguém acompanha se a pessoa melhorou. A avaliação formal é feita em planilha, com cobrança e consolidação manuais, e o resultado chega meses depois, sem comparação.

Todos os achados se encaixam em requisitos que **já existem** na lista geral. Os questionários não exigem um RF novo. Eles reforçam prioridades e trazem dois pontos de conflito (anonimato e acesso do RH) e três sugestões que hoje estão fora do escopo.

## 2 Achados e requisitos

Situação: **confirma** (o requisito atende ao achado), **reforça** (o achado aumenta a prioridade ou detalha o requisito) ou **conflito** (os respondentes divergem do que está na lista).

| ID | Achado | Evidência | Requisitos | Situação |
|---|---|---|---|---|
| A01 | O feedback informal não é registrado e se perde até a avaliação anual. | Q1 P03, P05; Q2 P03 | RF06, RF20, RF22 | Confirma |
| A02 | Os feedbacks não citam fatos; o receptor não sabe o que mudar. | Q1 P04 = 3; Q2 P04 = 2, P05 | RF06 (fato obrigatório), RF07, RN01 | Confirma |
| A03 | Registrar precisa ser rápido: 1 a 3 min (gestora) e menos de 1 min (colaborador). | Q1 P06; Q2 P06 | RF06 (tela única), RNF05 | Reforça |
| A04 | Feedback enviado não deve ser editado nem excluído, mas o receptor quer poder responder. | Q1 P07; Q2 P07 | RF08, RN02 | Confirma |
| A05 | Depois do feedback construtivo, as ações são combinadas de boca ou nada acontece. | Q1 P08; Q2 P08 | RF10, RF12, RF13 | Confirma |
| A06 | Ninguém volta para conferir se a pessoa melhorou. | Q1 P08 | RF14, RF15 | Confirma |
| A07 | Lembretes são úteis (notas 5 e 4), desde que dentro do sistema e não por e-mail. | Q1 P09; Q2 P09 | RF11, RF14 (decisão do grupo: notificações só na plataforma) | Confirma |
| A08 | A avaliação formal é feita em planilha; o RH cobra quem não respondeu e consolida à mão. | Q1 P10; Q2 P10 | RF16, RF18, RN06 | Confirma |
| A09 | O resultado demora meses e não compara autoavaliação com a visão dos colegas (notas 5 e 5 para a comparação). | Q1 P10, P12; Q2 P10, P12 | RF17, RF19 | Reforça |
| A10 | O colaborador quer saber "em que aspecto" melhorar, não só a competência. | Q2 P05 | RF12 (objetivo com indicador), RF05 | Reforça |
| A11 | Anonimato: a gestora quer opcional e quer assinar o que escreve; o colaborador quer anonimato sempre entre colegas. | Q1 P11; Q2 P11 | RF16, RN03 | Conflito |
| A12 | O colaborador prefere que o RH veja seus feedbacks só quando necessário; a gestora inclui o RH. | Q1 P14; Q2 P14 | RN04, RNF02 | Conflito |
| A13 | O colaborador usa mais o celular, porque atende fora do escritório. | Q2 P13 | RNF01 | Reforça |
| A14 | A gestora quer ver quem está há muito tempo sem feedback e quem tem plano atrasado. | Q1 P15 | RF21 | Confirma |
| A15 | O colaborador quer ver tudo o que recebeu e o que precisa melhorar num lugar só. | Q2 P15 | RF20, RF22 | Confirma |

## 3 Conflitos para o grupo decidir

1. **Anonimato (A11).** A lista geral já deixa o anonimato **opcional**, escolhido pelo gestor na rodada (RF16), e o gestor sempre identificado (RN03). Isso atende a gestora. O colaborador pediu anonimato **sempre**. Proposta: manter a RN03 como está, mas sugerir na tela de criação da rodada que o anonimato entre pares venha **ligado por padrão**.
2. **Acesso do RH (A12).** Tem relação com o ponto 2 da seção 10 da lista geral. A RN04 dá ao RH acesso a tudo. O colaborador aceita esse acesso "só se for necessário". Proposta: manter a RN04, mas registrar cada consulta do RH ao histórico de um colaborador (apoia a RNF02 e a RNF04) e deixar claro ao usuário quem pode ver os seus dados.

## 4 Sugestões para a lista geral

Pedidos que não têm requisito na lista geral. Ficam **sem ID** até o Caique e o grupo decidirem se entram.

| Sugestão | Evidência | Situação na lista geral |
|---|---|---|
| Relatório para levar à diretoria | Q1 P15 | Fora do escopo (seção 7: "relatórios e exportação para o RH"). Manter fora; o painel "Meu time" (RF21) cobre a necessidade do dia a dia. |
| Solicitar feedback a alguém | Q2 P15 | Fora do escopo (seção 7: "solicitar feedback"). Candidata para uma próxima versão, porque veio do colaborador e combate a dor "quase nunca recebo feedback". |
| Confirmação de leitura do feedback | Q2 P10 ("não sei se alguém leu") | Não aparece na lista. Pode ser resolvida dentro do RF09, mostrando ao emissor se o receptor já visualizou. |

## 5 Conclusão

- Os questionários **validam** o escopo da lista geral, principalmente RF06 (fato obrigatório em uma tela só), RF12 a RF15 (plano de ação com check-ins) e RF19 (comparar autoavaliação com a média dos outros).
- As maiores prioridades para quem respondeu são: registrar rápido (RF06, RNF05), acompanhar o plano (RF14) e ver o histórico num lugar só (RF20, RF21, RF22).
- As dores levantadas aqui alimentam o [BPMN do processo atual](bpmn-processo-avaliacao.md) (dores D01 a D08).
