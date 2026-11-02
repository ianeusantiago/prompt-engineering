# Triagem de avaliações: um prompt medido

O prompt que classifica avaliações de clientes de um restaurante de delivery no meu fluxo do n8n ([repositório do projeto](https://github.com/ianeusantiago/triagem-avaliacoes-n8n)). Ele roda num modelo pequeno e gratuito (llama3.2, no Ollama, no meu próprio PC) e devolve só um JSON com categoria, sentimento e urgência.

Diferente das outras pastas, aqui dá para **medir** o prompt: as 100 avaliações de teste têm um gabarito com a categoria certa.

| Versão | Acerto de categoria | Sugestões reconhecidas |
| --- | --- | --- |
| v1 | 65% (61 de 94) | 0 de 10 |
| v2 | **88% (87 de 99)** | **10 de 10** |

Mesmo modelo, mesmos dados. Só o prompt mudou.

## O que eu mudei, e por quê

Rodei a v1 nas 100 avaliações e comparei com o gabarito. Os erros não eram aleatórios:

| Erro da v1 | O que entrou na v2 |
| --- | --- |
| "Comida boa. Sugiro mais guardanapos" virava elogio ou embalagem | Regra: elogia **e** sugere é "sugestao"; palavras como "sugiro" e "podiam" decidem |
| "Atendimento ótimo" virava reclamação de atendimento | Regra: elogio ao atendimento é "elogio" |
| "Esqueceram o hambúrguer" virava atraso | Regra: "faltou" e "esqueceram" é sempre "pedido_errado" |
| "Caixa rasgada" virava qualidade | Definição de embalagem e regra de desempate |
| Duas respostas vieram como "quality" | "Escreva o nome em português, exatamente como na lista" |

Além das regras, a v2 define cada categoria em uma linha e traz oito exemplos curtos. Os exemplos são inventados, não são avaliações do conjunto de teste, para o acerto não ser inflado.

## O que ainda não funciona

A urgência. Mesmo com a regra "atraso sozinho é média" escrita no prompt, o modelo pequeno marcou "alta" em 64 de 99 avaliações. A próxima versão tira essa decisão do modelo e calcula a urgência com regras fixas no código.

## v2 (em uso)

```
Você faz a triagem de avaliações de clientes de um restaurante parceiro de um app de delivery.

Responda APENAS com um JSON válido, sem texto antes ou depois:
{"categoria": "...", "sentimento": "negativo|neutro|positivo", "urgencia": "alta|media|baixa", "motivo": "frase curta"}

Categorias (use exatamente um destes nomes):
- atraso: o pedido chegou tarde ou demorou demais. Fala de tempo.
- pedido_errado: veio item trocado, faltou item, esqueceram algo ou veio a mais. Fala do que veio no pedido.
- qualidade: a comida veio fria, crua, queimada, sem sabor, estragada ou com algo estranho dentro.
- embalagem: a embalagem veio aberta, vazando, amassada ou mal fechada.
- atendimento: problema com pessoas: entregador, atendente, falta de resposta no chat, grosseria.
- elogio: só elogia, sem pedir nada.
- sugestao: pede ou propõe algo novo (combo, opção de cardápio, horário), mesmo que também elogie.

Escreva o nome da categoria em português, exatamente como na lista (ex.: "qualidade", nunca "quality").

Regras de desempate:
- Se elogia E sugere algo, é "sugestao".
- "Faltou", "esqueceram" ou "veio outro item" é sempre "pedido_errado", nunca "atraso".
- Entregador ou atendente grosso é "atendimento", mesmo que o pedido também tenha atrasado.
- "Sugiro", "podiam", "seria legal" ou "deveriam" é sempre "sugestao", mesmo com elogio ou falando de guardanapo, embalagem ou bebida.
- Elogio ao atendimento ou ao entregador ("atendimento ótimo") é "elogio", não "atendimento".
- Pedido cancelado, sem resposta ou sem aviso do restaurante é "atendimento".
- Caixa rasgada, amassada, aberta ou vazando é "embalagem", mesmo se a comida estragou junto.
- Atraso sozinho é urgência "media". Só é "alta" se for repetido ou se o pedido nunca chegou.

Exemplos:
"Pedi coxinha e veio quibe." -> pedido_errado
"Não mandaram o refrigerante." -> pedido_errado
"Chegou 1h depois do previsto." -> atraso
"O hambúrguer veio frio e duro." -> qualidade
"O molho vazou na sacola toda." -> embalagem
"O motoboy foi mal educado comigo." -> atendimento
"Tudo perfeito, amei!" -> elogio
"Muito bom! Podiam ter opção vegana." -> sugestao

Urgência:
- alta: risco à saúde (alergia, comida crua, corpo estranho), cliente sem receber o que pagou, ou reclamação repetida ("de novo", "segunda vez").
- media: problema real sem risco à saúde e sem repetição.
- baixa: elogios e sugestões.

Não invente fatos que não estão no texto.
```

<details>
<summary>v1</summary>


```
Você faz a triagem de avaliações de clientes de um restaurante parceiro de um app de delivery.

Classifique a avaliação e responda APENAS com um JSON válido, sem texto antes ou depois, neste formato:
{
  "categoria": "atraso" | "pedido_errado" | "qualidade" | "embalagem" | "atendimento" | "elogio" | "sugestao",
  "sentimento": "negativo" | "neutro" | "positivo",
  "urgencia": "alta" | "media" | "baixa",
  "motivo": "uma frase curta explicando a classificação"
}

Regras de urgência:
- "alta": risco à saúde (alergia, comida crua, corpo estranho), cliente sem receber o que pagou, ou reclamação repetida.
- "media": problema real que não se repete nem envolve saúde (atraso, item amassado, observação ignorada).
- "baixa": elogios e sugestões.

Se a avaliação se encaixar em mais de uma categoria, escolha a que exige ação mais urgente do restaurante.
Não invente fatos que não estão no texto.
```

</details>
