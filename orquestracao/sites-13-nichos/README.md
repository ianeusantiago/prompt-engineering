# Orquestrador dos 13 sites

Uma equipe de agentes de IA que produz 13 sites de nichos diferentes (clínica, salão, hamburgueria, imobiliária e outros) e um site de portfólio, reproduzindo a estrutura de sites de referência e adaptando o conteúdo para cada nicho.

Eu supervisionei a equipe: rodei o prompt do orquestrador no [Orca](https://github.com/stablyai/orca), com cada agente no Claude Code, no próprio terminal e na própria git worktree. O deploy foi na Vercel, sempre com a minha aprovação. Os 14 sites estão no ar (links abaixo).

| Arquivo | Para quê |
| --- | --- |
| [`orchestrator-prompt.md`](orchestrator-prompt.md) | Prompt mestre do orquestrador: dados do projeto, equipe, fases, formato de delegação e regras |
| [`CLAUDE.md`](CLAUDE.md) | Regras que todo agente lê antes de agir: estrutura de pastas, código, git e o que precisa de aprovação |

## Os sites no ar

O portfólio da Koda reúne os 13 sites: **[koda-portfolio-two.vercel.app](https://koda-portfolio-two.vercel.app/)**

| # | Nicho | Site |
| --- | --- | --- |
| 01 | Clínica odontológica | [Sorriso Ateliê Odontologia](https://sorriso-atelie-odontologia.vercel.app/) |
| 02 | Cabeleireiro | [Casa Aurora Cabelos](https://casa-aurora-cabelos.vercel.app/) |
| 03 | Salão | [Salão Lumina](https://salao-lumina.vercel.app/) |
| 04 | Alimentação e bebidas | [Cervejaria Serra Alta](https://cervejaria-serra-alta.vercel.app/) |
| 05 | Educação | [Ponte Educação](https://ponte-educacao.vercel.app/) |
| 06 | Vestuário e acessórios | [Ateliê Garoa](https://atelie-garoa.vercel.app/) |
| 07 | Profissionais autônomos | [Faro Estúdio](https://faro-estudio-six.vercel.app/) |
| 08 | Arquitetura | [Traço Norte Arquitetura](https://traco-norte-arquitetura.vercel.app/) |
| 09 | Restaurante | [Restaurante Quintal da Serra](https://restaurante-quintal-da-serra.vercel.app/) |
| 10 | Hamburgueria | [Brasa Smash Hamburgueria](https://brasa-smash-hamburgueria.vercel.app/) |
| 11 | Sistema de produtos | [Fluxo Gestão](https://fluxo-gestao-xi.vercel.app/) |
| 12 | Cardápio online | [Cardápio Mandacaru](https://cardapio-mandacaru.vercel.app/) |
| 13 | Imobiliária | [Alicerce Imóveis](https://alicerce-imoveis.vercel.app/) |
| 14 | Portfólio | [Koda](https://koda-portfolio-two.vercel.app/) |

### Outros sites feitos com orquestração de agentes

De um projeto anterior, com o mesmo jeito de trabalhar. Os prompts desse projeto não foram guardados.

- [Brasa 84 Hamburgueria](https://brasa84.vercel.app/)
- [Horizonte Imóveis](https://horizonte-imoveis-livid.vercel.app/)
- [Moura & Rezende Advogados](https://moura-rezende.vercel.app/)
- [Clínica Sorriso](https://clinica-sorriso-rouge.vercel.app/)

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
