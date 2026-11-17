# BPMN do processo de avaliação (processo atual)

Sistema web de feedback e desenvolvimento de competências.

Versão 0.1, 17/11/2026. Responsável: Gabriel Mendes (P4). Os IDs seguem a [Lista Geral de Requisitos](../requisitos/requisitos.md).

## 1 Sobre o diagrama

O diagrama está em [`bpmn-processo-avaliacao.drawio`](bpmn-processo-avaliacao.drawio). Ele pode ser aberto em [app.diagrams.net](https://app.diagrams.net) ou na extensão Draw.io do VS Code. Foi feito com a notação BPMN 2.0 e mostra o processo **atual (AS-IS)**, como ele acontece hoje, **sem o sistema**. As dores aparecem como anotações em vermelho (D01 a D08).

O arquivo tem duas páginas:

| Página | Raias | O que mostra |
|---|---|---|
| Feedback do dia a dia (atual) | Gestor, Colaborador | Feedback informal, positivo ou construtivo, e o que acontece depois dele |
| Avaliação formal anual (atual) | RH, Gestor, Colaborador | Avaliação anual em planilha, da distribuição até o resultado |

Fonte: entrevista com Adriana Silveira de Souza ([transcrição](../elicitacao/entrevista-01-transcricao.md) e resumo na seção 2 da [lista geral](../requisitos/requisitos.md)). Os questionários de elicitação ainda não foram aplicados, então não entram como evidência.

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
| D01 | Os fatos ficam no papel, no Excel ou na memória e se perdem até a avaliação. | Anotar o fato | Entrevista: o registro manual se perde | RF06, RF22 |
| D02 | A conversa é marcada por fora, sem lembrete, e acaba adiada ou esquecida. | Marcar conversa | Entrevista: agendar a sessão e enviar lembrete | RF11 |
| D03 | O feedback é genérico, sem fato concreto, e o receptor não sabe o que mudar. | Dar o feedback | Entrevista: o fato é obrigatório; "melhorar a comunicação" precisa de um aspecto | RF06, RF07, RN01 |
| D04 | As ações são combinadas de boca, sem prazo nem registro. | Combinar ações | Entrevista: o plano é feito pelos dois | RF10, RF12, RF13 |
| D05 | Não há check-ins; ninguém sabe se a pessoa melhorou. | Acompanhar quando lembrar | Entrevista: pontos de monitoramento e encerramento | RF14, RF15 |
| D06 | Ninguém vê, num só lugar, quem não respondeu a avaliação. | Cobrar pendentes | Entrevista: registrar quem não preencheu, sem punir no sistema | RF18, RN06 |
| D07 | O resultado não compara a autoavaliação com a visão dos outros. | Consolidar o resultado | Entrevista: 360 do time, com autoavaliação comparada | RF16, RF17, RF19 |
| D08 | Não há histórico nem evolução, e o gestor não vê quem ficou sem feedback. | Acompanhar o time | Entrevista: visão dos últimos seis meses e evolução do indicador | RF20, RF21, RF22 |

## 5 Como o sistema muda o processo

Com o sistema, o roteiro da lista geral (**coletar fatos → dar o feedback → combinar um plano de ação → acompanhar com check-ins → encerrar**) passa a ser registrado de ponta a ponta:

- o fato é obrigatório e fica salvo no próprio feedback (D01, D03);
- a conversa e os check-ins geram lembretes na plataforma (D02, D05);
- o plano de ação nasce do feedback construtivo e é editado pelos dois (D04);
- a rodada de avaliação mostra quem respondeu e compara a autoavaliação com a média dos outros ao fim do prazo (D06, D07);
- "Meu desenvolvimento", "Meu time" e o histórico com gráfico de evolução substituem as planilhas (D08).

O registro do feedback informal no sistema está descrito no [caso de uso UC04](../casos-de-uso/uc04-registrar-feedback-informal.md).
