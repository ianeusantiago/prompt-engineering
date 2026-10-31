# Orquestrador dos 13 sites

Uma equipe de agentes de IA que produz 13 sites de nichos diferentes (clínica, salão, hamburgueria, imobiliária e outros) e um site de portfólio, reproduzindo a estrutura de sites de referência e adaptando o conteúdo para cada nicho.

Eu supervisionei a equipe: rodei o prompt do orquestrador no [Orca](https://github.com/stablyai/orca), com cada agente no Claude Code, no próprio terminal e na própria git worktree. O código fica no GitHub e o deploy é na Vercel, sempre com a minha aprovação.

| Arquivo | Para quê |
| --- | --- |
| [`orchestrator-prompt.md`](orchestrator-prompt.md) | Prompt mestre do orquestrador: dados do projeto, equipe, fases, formato de delegação e regras |
| [`CLAUDE.md`](CLAUDE.md) | Regras que todo agente lê antes de agir: estrutura de pastas, código, git e o que precisa de aprovação |

## Como a equipe é organizada

| Agente | Faz | É dono de |
| --- | --- | --- |
| Orquestrador | Planeja, delega, revisa e junta no `main` | `docs/INDEX.md`, `docs/logs/status.md` |
| Analyst | Documenta cada site de referência | `docs/specs/` |
| Designer | Monta os tokens de design | `docs/design/` |
| Content Writer | Adapta os textos para o nicho | `docs/content/` |
| Developer (1 a 3) | Constrói os sites | `shared/`, `sites/` |
| QA & Release | Testa, tira prints e prepara o deploy | `scripts/`, `docs/screenshots/` |

## Decisões que valem a pena olhar

- **Sem criatividade:** a IA não inventa seções, cores ou textos. O que falta vira `[TODO]` e uma pergunta para mim.
- **Delegação com formato fixo:** objetivo, entradas, saída e "pronto quando" em toda tarefa.
- **Só o orquestrador junta e faz push.** Os agentes nunca mexem no remoto.
- **Login, deploy e criação de repositório esperam a minha aprovação.**
- **Nada de logos, textos ou fotos dos sites de referência:** só a estrutura é reproduzida.

As URLs dos sites de referência foram removidas desta versão pública.
