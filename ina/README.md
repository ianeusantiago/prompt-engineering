# INA

[INA](https://github.com/ianeusantiago/Ina) é um app desktop para Windows que orquestra uma equipe de agentes de IA: um orquestrador e vários agentes, cada um rodando o Claude Code no próprio terminal e na própria git worktree.

O app foi construído com o Claude Code a partir destes dois arquivos. Hoje ele está na versão 0.1.1, com instalador, atualização automática e CI no Windows.

| Arquivo | Para quê |
| --- | --- |
| [`PROMPT.md`](PROMPT.md) | Prompt mestre: produto, stack, arquitetura, regras de orquestração, segurança e qualidade |
| [`CLAUDE.md`](CLAUDE.md) | Regras do projeto, que têm prioridade sobre o prompt: estilo, fluxo de aprovação, segurança e os comandos PAUSAR e RETOMAR |

## Decisões que valem a pena olhar

- **Plano antes de código:** a fase 0 precisa da minha aprovação antes de criar qualquer arquivo.
- **"Nunca dizer que funciona sem rodar e ver a saída."**
- **Segurança desde o prompt:** o backend é a única autoridade sobre processos, sem comandos montados como texto.
- **PAUSAR e RETOMAR:** o estado do projeto fica em `docs/STATE.md`, para continuar em outra sessão sem perder o contexto.
