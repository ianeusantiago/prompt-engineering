# Prompts

Prompts e arquivos de contexto que eu uso para orquestrar agentes de IA de programação (principalmente o [Claude Code](https://docs.claude.com/claude-code)) em projetos reais: um app desktop, um conjunto de 13 sites e um jogo no Roblox.

**Como eu trabalho:** escrevo o objetivo e as regras, uso o ChatGPT para rascunhar e organizar o texto, reviso e ajusto cada parte, e aplico no Claude Code. Quando a IA erra, volto ao prompt e mudo a regra que deixou o erro acontecer.

## O que tem aqui

| Pasta | Projeto | O que mostra |
| --- | --- | --- |
| [`ina/`](ina/) | [Iná](https://github.com/ianeusantiago/Ina), app desktop que orquestra agentes de IA | O prompt que gerou o app e as regras do projeto (`CLAUDE.md`) |
| [`orquestracao/sites-13-nichos/`](orquestracao/sites-13-nichos/) | 13 sites de nichos diferentes + portfólio, feitos por uma equipe de agentes | Um orquestrador que delega para 5 papéis, cada um no próprio terminal e git worktree |
| [`jogo-roblox/`](jogo-roblox/) | SHIFT ZERO, jogo cooperativo no Roblox (protótipo) | Duas versões do prompt (v1 e v2) e o que mudou de uma para a outra |

## O que esses prompts têm em comum

1. **Papel e escopo claros.** Cada agente sabe o que faz, quais pastas são dele e o que não pode tocar.
2. **Dados do projeto dentro do prompt.** O agente não precisa perguntar o que já foi decidido.
3. **Regras escritas como "nunca".** Nunca inventar IDs, nunca fazer login, nunca dizer que testou o que não testou.
4. **Definição de pronto.** Cada tarefa termina com critérios verificáveis, não com "parece bom".
5. **Aprovação humana nas ações de risco.** Deploy, criar repositório, gastar dinheiro e apagar dados esperam o meu "sim".
6. **Arquivos como memória.** `CLAUDE.md`, `status.md` e registros de decisões guardam o estado do projeto, para não depender da conversa.
7. **Honestidade nos testes.** O agente precisa separar o que verificou do que só escreveu.

## Aviso

Os prompts estão como eu usei, em inglês, com pequenas edições para publicação: URLs de sites de referência removidas e e-mails trocados pelo meu. Os resultados de cada projeto estão descritos com honestidade no README de cada pasta, inclusive o que não deu certo.
