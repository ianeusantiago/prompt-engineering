# SHIFT ZERO (jogo no Roblox)

Um jogo cooperativo em que os jogadores mantêm funcionando uma máquina gigante que quebra o tempo todo. Feito com o Claude Code a partir destes dois prompts.

**Resultado:** o jogo ficou em protótipo, incompleto. O valor desta pasta está nos prompts e no que mudou entre as duas versões.

| Arquivo | Para quê |
| --- | --- |
| [`v1-mvp.md`](v1-mvp.md) | Construir do zero o primeiro jogo jogável (MVP) |
| [`v2-expansao.md`](v2-expansao.md) | Expandir o projeto existente sem jogar fora o que já funcionava |

## O que mudou da v1 para a v2

| Tema | v1 (MVP) | v2 (expansão) |
| --- | --- | --- |
| Ponto de partida | Criar o projeto | Auditar o projeto existente e preservar o que funciona |
| Duração | Turnos de cerca de 3 minutos | Partida de cerca de 20 minutos, com fase final |
| Jogadores | 1 a 8, entrando a qualquer momento | 1 a 6, com filas Solo a Time de 6 e servidores reservados para o grupo não se separar |
| Dificuldade | "Fica mais difícil" | Fórmula `1 + 1,5 × t^1,6`, com limites e janelas de recuperação |
| Defeitos da máquina | 5 eventos com efeito no cenário | 8 eventos, cada um com um minigame próprio, e uma checagem que acusa evento sem minigame |
| Loja | Cosméticos com a moeda do jogo | Loja de utilidades com efeito conhecido e limite de uso |
| Itens aleatórios | Caixas pagas proibidas | Caixas cosméticas ganhas jogando; as pagas só com as regras do Roblox (PolicyService) e chances mostradas item por item, somando 100% |

## Regras que aparecem nas duas versões

- O servidor decide tudo: o cliente nunca diz sozinho que ganhou, quanto tem de moeda ou qual recompensa recebeu.
- Não inventar IDs de produtos, de lugares ou de assets.
- Não dizer que testou no Roblox Studio ou com vários jogadores sem ter testado.
- Implementar, e não parar num documento de design.
