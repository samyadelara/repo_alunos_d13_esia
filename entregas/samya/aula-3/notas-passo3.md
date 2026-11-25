# Passo 3: o que a IA acrescentou e o que foi aproveitado

Base: `rodada1-ia.md` (Rodada 1), comparada com `caso/regras.md`, a demanda B e, depois, `caso/decisoes-confirmadas.md`.

## Acréscimos da IA (classificação da aluna, revisada pelo tutor)

| Item da resposta da IA | Origem |
|---|---|
| "pessoa nova na equipe que atende chamados" | Acréscimo. A própria IA marcou como dúvida |
| "atende chamados da Oficina e do Laboratório" | Acréscimo não marcado. Tensiona a R3 (só o próprio departamento) |
| "para conseguir classificar um chamado sozinha" | Acréscimo não marcado. A demanda pede explicar, não classificar sozinha |
| impacto e urgência de 1 a 3, somados; faixas | R1 |
| "toda soma de 2 a 6 tem uma faixa" | Derivado da R1. Exigir isso no texto é escolha de critério |
| "um exemplo para cada faixa" | Escolha de critério da IA |
| sem prazo, e-mail, administrador; `media` sem acento | regras.md, linha 12 |
| R4 | regras.md |
| não filtrar por departamento quando só se classifica prioridade | regras.md, linha 31 |

## O que a decisão B trouxe e ninguém previu

- Texto de até 120 palavras. Nem a aluna nem a IA previram.
- Exemplos de soma 4 e 5: coincidem com o C2 do passo 1.
- A decisão não diz quem é a pessoa nova: a hipótese continua hipótese.

## Ajustes da aluna depois da decisão

- C3 passou a usar só T3, e testa estado, não departamento (por causa das 120 palavras).
- Pessoa nova: "atende chamados do próprio departamento", para não conflitar com a R3.

## Sugestões da IA: aceitas e rejeitadas

| Item | Decisão | Motivo |
|---|---|---|
| Critério "a regra está completa" | Rejeitado | O nome é vago ("completa" = 9 combinações, 6 registros ou 3 faixas?) e só o "como conferir" esclarece. As três faixas já estão exigidas na Saída esperada |
| Critério 3 da IA: "procurar esses termos no texto" | Rejeitado | O problema não é o termo aparecer, é ele influenciar a classificação. Um texto que diga "o departamento não altera a prioridade" falharia sem ter erro. Busca de termo serve para checar formato (`media` sem acento), não a classificação |
| Mencionar que R2 e R3 são assuntos separados | Aceito, reescrito | Reforça o contrato. Entrou na Saída esperada como "estado e departamento não entram no cálculo da prioridade", em linguagem da pessoa nova |
| Tabela de somas de 2 a 6 | Não incluído | Decisão da aluna. Motivo: [PREENCHER] |
| Exemplo 1 + 2 = 3 | Não incluído | Decisão da aluna. Motivo: [PREENCHER] |
| Dúvida: formato da explicação | Respondida | Decisão B: texto de até 120 palavras |
| Dúvida: por que as faixas são essas | Registrada | Entrou em "Limites e dúvidas" da v1 |
