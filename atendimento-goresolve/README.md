# GoResolve: o prompt de uma equipe de agentes

O prompt do orquestrador que usei para construir, em um dia e sozinho, o [GoResolve](https://goresolve.vercel.app): um agente que triagem conversas de atendimento de uma varejista de moda e beleza. A IA lê a conversa e classifica; o código decide a ação pela política; uma pessoa aprova o que passa do limite.

O prompt completo está em [`orchestrator-prompt.md`](orchestrator-prompt.md).

## O que ele define

- **Quatro agentes, cada um dono de uma pasta:** analista (produto e dados), construtor (fluxo e telas), verificador (tenta provar que está errado) e documentador.
- **Economia de tokens escrita no prompt:** no máximo dois agentes ativos ao mesmo tempo, o modelo de cada um definido na criação (analista em Sonnet, construtor e verificador em Opus, documentador em Haiku), esforço baixo para todos, e encerrar quem ficar ocioso.
- **A decisão de negócio fica no código.** O prompt manda a IA só interpretar o texto livre; ação, alçada e prazo vêm de regras lidas de `politicas.csv`, e toda saída do modelo passa por um schema. Saída inválida ou incerta vai para uma pessoa.
- **Fatos dos dados dentro do prompt** (custos, limites de alçada, prazos), para o agente não perguntar o que já foi decidido.
- **Fases com parada para revisão:** o analista entrega o SPEC e os casos, e eu reviso antes de o construtor começar.
- **Regras de honestidade:** nunca dizer que funciona sem executar, marcar o que não foi testado como NÃO VERIFICADO e registrar cada erro relevante da IA.

## Resultado

Medido com 15 casos de avaliação criados a partir de conversas reais e com a fila do dia (65 conversas):

| | |
| --- | --- |
| Conversas resolvidas sem pessoa | **59 de 65** |
| Casos de avaliação corretos | **14 de 15** |
| Testes automatizados | 476 |

## O que ainda falha

Um caso: a IA não marcou a dúvida sobre a elegibilidade de um cupom, então o agente validou o cupom em vez de também chamar uma pessoa. Deixei como está, de propósito. A regra no código estava certa e testada, e mudar o prompt até o caso passar (ou editar o gabarito) seria ajustar ao teste. O erro e o que mudei no processo estão no `ERROS.md` do projeto.

## Aviso

O prompt está como usei, com pequenas edições para publicação: nomes de empresas e do evento, detalhes do ambiente de acesso e os critérios de avaliação foram removidos. Os dados do projeto são fictícios.
