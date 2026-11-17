# BPMN do processo de avaliação (processo atual)

Sistema web de feedback e desenvolvimento de competências.

Versão 0.1, 17/11/2026. Responsável: Gabriel Mendes (P4). Os IDs seguem a [Lista Geral de Requisitos](requisitos.md).

## 1 Sobre o diagrama

O diagrama está em [`bpmn-processo-avaliacao.drawio`](bpmn-processo-avaliacao.drawio). Ele pode ser aberto em [app.diagrams.net](https://app.diagrams.net) ou na extensão Draw.io do VS Code. Foi feito com a notação BPMN 2.0 e mostra o processo **atual (AS-IS)**, como ele acontece hoje, **sem o sistema**. As dores aparecem como anotações em vermelho (D01 a D08).

O arquivo tem duas páginas:

| Página | Raias | O que mostra |
|---|---|---|
| Feedback do dia a dia (atual) | Gestor, Colaborador | Feedback informal, positivo ou construtivo, e o que acontece depois dele |
| Avaliação formal anual (atual) | RH, Gestor, Colaborador | Avaliação anual em planilha, da distribuição até o resultado |

Fontes: entrevista com a professora (resumo na seção 2 da [lista geral](requisitos.md)) e os [questionários aplicados](questionarios.md) (Q1: gestora; Q2: colaborador).

## 2 Feedback do dia a dia

1. O gestor observa uma situação e **anota o fato** num caderno, numa planilha pessoal ou só na memória.
2. Se decide não dar feedback, o fato é esquecido. Se decide dar, **marca a conversa** por WhatsApp ou pela agenda.
3. Na conversa, o gestor **dá o feedback** e o colaborador **ouve**. Nada fica por escrito para o colaborador.
4. Se o feedback é **positivo**, o processo termina sem registro.
5. Se é **construtivo**, os dois **combinam ações de boca**. O colaborador **tenta aplicá-las sozinho** e o gestor **acompanha quando lembra**. O resultado (melhorou ou não) não é registrado.

## 3 Avaliação formal anual

1. No início do ciclo anual, o RH **envia uma planilha de avaliação** por e-mail.
2. Em paralelo, o gestor **avalia cada pessoa do time** e o colaborador **faz a autoavaliação e avalia dois colegas**, tudo em planilha.
3. O RH **confere as planilhas recebidas**. Enquanto falta alguém, **cobra os pendentes** por e-mail e WhatsApp e confere de novo.
4. Quando todos respondem, o RH **consolida as respostas à mão** e, meses depois, **envia o resultado ao gestor**.
5. O gestor **repassa o resultado** ao colaborador, que o recebe **sem comparação** com a autoavaliação e **sem histórico** dos anos anteriores.

## 4 Principais dores

| Dor | Descrição | Onde ocorre | Evidência | Requisitos que resolvem |
|---|---|---|---|---|
| D01 | Os fatos ficam no papel, no Excel ou na memória e se perdem até a avaliação. | Anotar o fato | Entrevista (dor principal); Q1 P03, P05; Q2 P03 | RF06, RF22 |
| D02 | A conversa é marcada por fora, sem lembrete, e acaba adiada ou esquecida. | Marcar conversa | Entrevista (agendar com lembrete); Q1 P09 | RF11 |
| D03 | O feedback é genérico, sem fato concreto, e o receptor não sabe o que mudar. | Dar o feedback | Entrevista (feedback sempre com fatos); Q2 P04, P05 | RF06, RF07, RN01 |
| D04 | As ações são combinadas de boca, sem prazo nem registro. | Combinar ações | Entrevista (plano feito em conjunto); Q1 P08; Q2 P08 | RF10, RF12, RF13 |
| D05 | Não há check-ins; ninguém sabe se a pessoa melhorou. | Acompanhar quando lembrar | Entrevista (check-ins e encerramento); Q1 P08 | RF14, RF15 |
| D06 | O RH cobra as pendências uma a uma e ninguém vê quem não respondeu. | Cobrar pendentes | Entrevista (registrar quem não respondeu); Q1 P10 | RF18, RN06 |
| D07 | A consolidação é manual, o resultado demora meses e não compara a autoavaliação com a visão dos outros. | Consolidar à mão | Entrevista (360 com autoavaliação comparada); Q1 P10; Q2 P10, P12 | RF16, RF17, RF19 |
| D08 | Não há histórico nem evolução por competência, e o gestor não vê quem ficou sem feedback. | Receber o resultado | Entrevista (visão do time nos últimos 6 meses; evolução ao longo do tempo); Q1 P15; Q2 P15 | RF20, RF21, RF22 |

## 5 Como o sistema muda o processo

Com o sistema, o roteiro da lista geral (**coletar fatos → dar o feedback → combinar um plano de ação → acompanhar com check-ins → encerrar**) passa a ser registrado de ponta a ponta:

- o fato é obrigatório e fica salvo no próprio feedback (D01, D03);
- a conversa e os check-ins geram lembretes na plataforma (D02, D05);
- o plano de ação nasce do feedback construtivo e é editado pelos dois (D04);
- a rodada de avaliação mostra quem respondeu e compara a autoavaliação com a média dos outros ao fim do prazo (D06, D07);
- "Meu desenvolvimento", "Meu time" e o histórico com gráfico de evolução substituem as planilhas (D08).

O registro do feedback informal no sistema está descrito no [caso de uso UC04](caso-de-uso-registrar-feedback-informal.md).
