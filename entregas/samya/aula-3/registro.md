# Registro da prática da aula 3

Demanda B: "Preciso explicar como a prioridade funciona". Data: 23/11/2026.

Como foi feito: a prática foi refeita fora da aula, com o Claude Code como tutor. A Rodada 1 (IA) e a execução da v1 foram feitas em sessões separadas do Claude Code. A conferência dos critérios foi uma inspeção manual da própria autora, sem colega disponível.

## 1. O que a IA acrescentou

Resposta da Rodada 1 em `rodada1-ia.md`, comparada com `caso/regras.md`, a demanda B e, depois, `caso/decisoes-confirmadas.md`.

| Acréscimo da IA | Marcado pela IA como suposição? | Problema |
|---|---|---|
| A pessoa nova é "da equipe que atende chamados" | Sim, nas dúvidas | A demanda e a decisão B não dizem quem é a pessoa |
| Ela atende chamados "da Oficina e do Laboratório" | Não | Tensiona a R3: uma pessoa só vê chamados do próprio departamento |
| O objetivo é "classificar um chamado sozinha" | Não | A demanda pede explicar. A própria IA pergunta isso nas dúvidas |

Nem a IA nem a autora previram o limite de 120 palavras da decisão B.

## 2. Sugestões da IA: aceita e rejeitadas

| Sugestão | Decisão | Motivo |
|---|---|---|
| Mencionar que R2 e R3 são assuntos separados | Aceita, reescrita | Reforça o contrato. Entrou na Saída esperada como "estado e departamento não entram no cálculo da prioridade", em linguagem da pessoa nova |
| Critério "a regra está completa" | Rejeitada | O nome é vago ("completa" = 9 combinações, 6 registros ou 3 faixas?) e só o "como conferir" esclarece. As três faixas já estão exigidas na Saída esperada |
| Critério "procurar esses termos no texto" | Rejeitada | O problema não é o termo aparecer, é ele influenciar a classificação. Um texto que diga "o departamento não altera a prioridade" falharia sem ter erro. Busca de termo serve para checar formato (`media` sem acento), não a classificação |

## 3. Critério reescrito: C3

C3 original (v1):

| Dada esta entrada | Deve acontecer | Como vou conferir |
|---|---|---|
| T3: estado `fechado`, impacto 3, urgência 3 | O texto mostra 3 + 3 = 6 → `alta`, sem dizer que o estado muda ou impede a classificação | Refazer a soma pela R1. Procurar menção a estado como fator de prioridade (regras.md, linha 31) |

O que a execução mostrou (`resposta-colega.md`): o C3 passou pelo escrito, mas o texto nunca diz que o T3 está `fechado`. O executor omitiu o estado de propósito, para não parecer que ele influencia a prioridade. O critério não exigia mostrar o estado, então não conferia a intenção: mostrar que um chamado fechado continua sendo classificado.

C3 reescrito:

| Dada esta entrada | Deve acontecer | Como vou conferir |
|---|---|---|
| T3: estado `fechado`, impacto 3, urgência 3; T6: estado `aberto`, impacto 2, urgência 3 | O texto mostra o estado de cada um ao lado da conta: T3 `fechado`, 3 + 3 = 6 → `alta`; T6 `aberto`, 2 + 3 = 5 → `alta`. Tanto o aberto quanto o fechado são classificados pela soma | Refazer as duas somas pela R1. Verificar que o estado aparece nos dois exemplos e que o texto não usa o estado para mudar ou impedir a classificação (regras.md, linha 31). Passa só se as três condições valerem |

O que mudou:
- entrou o T6 (`aberto`) como contraponto ao T3 (`fechado`);
- o estado passou a ser obrigatório no texto;
- o "como conferir" ganhou três condições objetivas.

O T6 já estava no texto (C2), então a mudança cabe nas 120 palavras.
