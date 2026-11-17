# Especificação Suplementar — ISO/IEC 25010

Sistema web de feedback e desenvolvimento de competências.

Versão 0.1, 17/11/2026. Responsável: Kezer. Situação: aguardando validação do grupo.

Este documento organiza os requisitos **não funcionais** pelas características de qualidade do produto da ISO/IEC 25010. Os requisitos funcionais ficam na [lista geral](requisitos.md); a ligação entre os dois está na [matriz de rastreabilidade](matriz-de-rastreabilidade.md).

## 1 Escopo e convenções

RNF01 a RNF06 já existem na lista geral e são aqui **reescritos de forma verificável**, sem mudar a intenção. RNF07 em diante são **novos** e precisam ser incorporados à lista geral pelo responsável por ela.

Todo requisito traz uma medida e um critério. Metas numéricas são de projeto, a validar: não representam desempenho medido.

A edição usada é a **ISO/IEC 25010:2023**, com nove características. Se a disciplina trabalhar com a edição de 2011, vale a correspondência:

| 2011 | 2023 |
|---|---|
| Usabilidade | Capacidade de interação |
| Portabilidade | Flexibilidade (com adaptabilidade e escalabilidade) |
| Segurança (*security*) | Segurança, agora com autenticidade e resistência |
| — | Segurança física (*safety*), característica nova |

## 2 Adequação funcional

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF07 | **Completude funcional.** Todo requisito da lista geral deve ter caso de uso e critério de verificação antes de ser considerado pronto | 100% dos RF com UC e CV preenchidos na matriz de rastreabilidade |
| RNF08 | **Correção funcional.** Médias por competência, comparação entre autoavaliação e média dos pares e contagem de dias desde o último feedback devem bater com o cálculo manual sobre a mesma massa | Divergência zero em 10 casos de teste; arredondamento só na exibição, com duas casas |
| RNF09 | **Adequação funcional.** Dar um feedback completo deve caber em uma única tela, sem navegação intermediária | Contagem de telas igual a 1, conforme RF06 |

## 3 Eficiência de desempenho

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF10 | **Tempo de resposta.** Consultas de cadastro, painel e histórico, com paginação | 95% das requisições em até 2 s, com 50 usuários simultâneos e base de 100.000 respostas, em ambiente de homologação documentado |
| RNF11 | **Capacidade.** Porte máximo previsto para uma organização | 1.000 usuários cadastrados, 50 times, 200 participantes por rodada de avaliação |
| RNF12 | **Uso de recursos.** Abertura de rodada e geração das avaliações não deve bloquear a aplicação | Operação transacional concluída em até 10 s para 200 participantes, sem indisponibilidade das demais telas |

## 4 Compatibilidade

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF13 | **Coexistência.** A aplicação deve funcionar nos navegadores de uso corrente na organização | Chrome, Firefox, Edge e Safari, nas duas versões mais recentes de cada, sem erro de layout nem de função |
| RNF14 | **Interoperabilidade.** Não há integração obrigatória com sistema de RH nesta versão. O cadastro inicial de usuários deve poder ser feito manualmente sem depender de importação | Caso de uso de cadastro manual concluído sem arquivo externo |

A entrevista levantou a hipótese de importar as pessoas de uma planilha. Isso está fora do escopo desta versão e permanece registrado como evolução.

## 5 Capacidade de interação

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF01 | **Adaptabilidade da interface.** Aplicação web responsiva, utilizável no computador e no celular pelo navegador | Sem rolagem horizontal entre 360 e 1.440 px de largura |
| RNF05 | **Operabilidade.** Dar um feedback em uma tela só, com linguagem simples, em português do Brasil | Verificado por RNF09 e por inspeção de texto da interface |
| RNF06 | **Acessibilidade.** Campos com rótulo associado, contraste adequado e navegação por teclado | Contraste mínimo de 4,5:1 para texto normal; todos os fluxos de preenchimento percorríveis só com teclado; sem erro de rótulo em verificador automático |
| RNF15 | **Reconhecibilidade e aprendizagem.** Um colaborador sem treinamento deve conseguir dar seu primeiro feedback apenas pela interface | Em teste com 10 pessoas, pelo menos 8 concluem em até 3 minutos sem ajuda |
| RNF16 | **Proteção contra erro do usuário.** Como o feedback é imutável após o envio (RN02), a interface deve exibir confirmação explícita antes de enviar, mostrando o que será gravado | Confirmação presente; cancelar preserva o texto já digitado |
| RNF17 | **Clareza do registro.** Erros de validação devem indicar o campo e a condição inválida, preservando os dados já preenchidos | Nenhum campo perdido após erro, em teste de formulário |

RNF16 vem direto da entrevista: foi perguntado o que acontece quando alguém escreve algo mal interpretado, e a resposta foi que o registro não se apaga. A proteção, então, tem de estar **antes** do envio.

## 6 Confiabilidade

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF18 | **Disponibilidade.** Serviço disponível no horário de trabalho da organização | 99% no mês, medido entre 8h e 18h em dias úteis |
| RNF19 | **Maturidade e tolerância a falhas.** Abertura de rodada, geração das avaliações e envio de resposta devem ser atômicos | Falha no meio da operação não deixa rodada parcialmente aberta nem envio pela metade; duas requisições simultâneas não geram duplicata |
| RNF20 | **Recuperabilidade.** Cópia de segurança e restauração verificadas | Backup diário; perda máxima de 24 h (RPO); restauração em até 4 h (RTO), comprovada por simulação registrada |

## 7 Segurança

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF03 | **Autenticidade e confidencialidade na transmissão.** Acesso apenas autenticado, senha armazenada com função de derivação de chave e comunicação por HTTPS | bcrypt, scrypt ou Argon2 com parâmetros registrados; nenhuma senha em texto puro em banco ou log; HTTPS em produção |
| RNF21 | **Confidencialidade.** Autenticação e autorização validadas **no servidor** em toda operação, segundo a visibilidade do RN04 | Acesso direto ao identificador de um registro de outro usuário é rejeitado, inclusive por chamada de API |
| RNF22 | **Integridade.** Feedback enviado e resposta enviada não podem ser alterados nem apagados | Tentativa de alteração rejeitada; ajuste só por comentário, conforme RN02 |
| RNF04 | **Não repúdio e rastreabilidade.** Registrar autor e instante de cada feedback, comentário, plano e check-in | Todo registro consultável com autor e data; usuário comum não altera nem apaga evento de auditoria |
| RNF23 | **Resistência.** Limitar tentativas de autenticação | Bloqueio temporário após 5 tentativas erradas consecutivas na mesma conta |
| RNF02 | **Privacidade (LGPD).** Coletar apenas o necessário, informar a finalidade ao usuário, permitir que ele consulte e peça correção dos próprios dados pessoais, e restringir acesso conforme RN04 | Aviso de finalidade presente no primeiro acesso; fluxo de consulta e de pedido de correção disponível ao titular; conteúdo de feedback ausente dos logs técnicos |
| RNF24 | **Anonimato parametrizável.** Quando o anonimato estiver ligado numa rodada, a interface não deve revelar o autor das respostas entre pares, e a tela deve informar ao respondente quem poderá ver o quê antes de ele responder | Autor não exposto na interface nem na resposta da API; aviso presente na tela |
| RNF25 | **Retenção.** Manter o histórico de feedbacks por 5 anos; após o desligamento da pessoa, manter pelo mesmo prazo e então tratar conforme a política definida | Política escrita e aplicada; ver LAC01 na matriz de rastreabilidade |

Dois pontos de atenção que a equipe precisa decidir, não apenas documentar:

- RNF24 esbarra no que a cliente disse sobre o RH ter acesso aos dados. Anonimato de interface com identificação no banco é uma promessa frágil, e isso deve ficar explícito na tela, não escondido.
- RNF25 contradiz o RN12 do IEEE 830 v0.1, que proíbe qualquer expurgo. Guardar para sempre não é conservador do ponto de vista da LGPD: é o oposto da minimização.

## 8 Manutenibilidade

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF26 | **Modularidade.** Regras de negócio (RN01 a RN06) implementadas em camada própria, independente da interface | Nenhuma regra duplicada entre interface e servidor, verificado por inspeção |
| RNF27 | **Testabilidade.** Regras de negócio e cálculos cobertos por teste automatizado | Cobertura de pelo menos 70% nas classes de regra e de cálculo |
| RNF28 | **Analisabilidade.** Logs técnicos devem permitir diagnosticar erro sem expor conteúdo de feedback | Nenhum texto de feedback, comentário ou credencial nos logs |

## 9 Flexibilidade

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF29 | **Adaptabilidade.** Competências, questionários, periodicidade das rodadas e prazos devem ser configuráveis pelo RH ou pelo gestor, sem alteração de código | Mudança realizada pela interface, sem implantação nova |
| RNF30 | **Instalabilidade.** Ambiente de desenvolvimento reproduzível | Aplicação sobe em máquina limpa seguindo o README, com script ou contêiner |
| RNF31 | **Escalabilidade.** O modelo de dados não deve impedir o crescimento do histórico | Consultas de histórico com índice e paginação; sem varredura completa de tabela nas telas de uso diário |

## 10 Segurança física (*safety*)

Não há risco físico direto, mas a característica é aplicável no sentido de **risco operacional ao usuário**, e esse risco foi o ponto que a cliente mais enfatizou: um feedback mal dado destrói em vez de desenvolver.

| ID | Requisito | Medida e critério |
|---|---|---|
| RNF32 | **Prevenção de risco operacional.** A interface deve conduzir o emissor à estrutura adequada do feedback e exigir o fato que o sustenta | Fato obrigatório (RN01) e roteiro exibido por tipo (RF07), verificados por CV04 e CV05 |
| RNF33 | **Delimitação de uso.** O sistema deve deixar claro que não é canal de denúncia; relatos dessa natureza devem ser direcionados ao canal próprio da organização | Texto de orientação presente na tela de feedback e na de resposta de rodada |

RNF33 responde diretamente à discussão sobre denúncias na entrevista, que terminou sem resposta da cliente. Registrar o limite na interface é mais honesto do que deixar a pessoa supor que está protegida.

## 11 Resumo por característica

| Característica | Requisitos | Novos |
|---|---|---|
| Adequação funcional | RNF07, RNF08, RNF09 | 3 |
| Eficiência de desempenho | RNF10, RNF11, RNF12 | 3 |
| Compatibilidade | RNF13, RNF14 | 2 |
| Capacidade de interação | RNF01, RNF05, RNF06, RNF15, RNF16, RNF17 | 3 |
| Confiabilidade | RNF18, RNF19, RNF20 | 3 |
| Segurança | RNF02, RNF03, RNF04, RNF21, RNF22, RNF23, RNF24, RNF25 | 5 |
| Manutenibilidade | RNF26, RNF27, RNF28 | 3 |
| Flexibilidade | RNF29, RNF30, RNF31 | 3 |
| Segurança física | RNF32, RNF33 | 2 |

Total: 33 requisitos, sendo 27 novos e 6 reescritos a partir da lista geral.

## 12 Pendências

1. Incorporar RNF07 a RNF33 à lista geral, mantendo a numeração desta especificação.
2. Resolver a contradição entre RNF25 e o RN12 do IEEE 830 v0.1.
3. Decidir até onde vai o anonimato do RNF24 diante do acesso do RH.
4. Confirmar com a professora se a disciplina trabalha com a edição de 2011 ou de 2023 da norma. As duas estão contempladas pela tabela da seção 1.
