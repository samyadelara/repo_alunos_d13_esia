# Especificação curta

Responsável: Samya · Versão: v2 · Data: 23/11/2026

Demanda B (`caso/demandas.md`): "Preciso explicar como a prioridade funciona".

## Necessidade e objetivo
Uma pessoa nova no time que atende chamados precisa de um texto curto que explique como a prioridade de um chamado é definida, para entender a classificação a partir do impacto e da urgência.

## Entradas e fonte da verdade
- `caso/regras.md`: R1, registros T1 a T6, linha 12 (`media` sem acento; não existe regra de prazo de atendimento) e linha 31 (não acrescentar filtro quando a tarefa é só classificar prioridade).
- `caso/decisoes-confirmadas.md`, decisão da demanda B.

## Limites e dúvidas
- Confirmado (decisão B): texto de até 120 palavras; não promete prazo de atendimento.
- Confirmado (R1): a prioridade depende só de impacto e urgência. `media` é escrito sem acento (regras.md, linha 12).
- Limite: o texto não define ordem de atendimento.
- Hipótese: a pessoa nova atende chamados do próprio departamento. A demanda e a decisão B não dizem quem é a pessoa.
- Dúvida: é preciso explicar por que as faixas são essas? O caso não traz essa justificativa.

## Saída esperada
Texto em Markdown, de até 120 palavras, nesta ordem:
1. a regra: impacto e urgência são inteiros de 1 a 3 e são somados;
2. as faixas: soma 2 → `baixa`; soma 3 ou 4 → `media`; soma 5 ou mais → `alta`;
3. os exemplos T4, T5, T6 e T3, com a soma e a prioridade de cada um, e o estado de T3 e T6;
4. a frase: estado e departamento não entram no cálculo da prioridade.

Contagem de palavras: os números contam. O título, os IDs (T1, T2...), os símbolos (+, =, →) e a marcação Markdown não contam.

## Critérios de aceite
| ID | Dada esta entrada | Deve acontecer | Como vou conferir |
|---|---|---|---|
| C1 (normal) | T4: impacto 1, urgência 1 | O texto mostra 1 + 1 = 2 → `baixa` | Refazer a soma pela R1: soma 2 → `baixa` |
| C2 (fronteira) | T5: impacto 2, urgência 2; T6: impacto 2, urgência 3 | O texto mostra 2 + 2 = 4 → `media` e 2 + 3 = 5 → `alta`, deixando claro que a faixa muda entre 4 e 5 | Refazer as duas somas pela R1 e conferir com a decisão B (exemplos de soma 4 e 5). Passa só se as duas classificações estiverem certas |
| C3 (exclusão) | T3: estado `fechado`, impacto 3, urgência 3; T6: estado `aberto`, impacto 2, urgência 3 | O texto mostra o estado de cada um ao lado da conta: T3 `fechado`, 3 + 3 = 6 → `alta`; T6 `aberto`, 2 + 3 = 5 → `alta`. Tanto o aberto quanto o fechado são classificados pela soma | Refazer as duas somas pela R1. Verificar que o estado aparece nos dois exemplos e que o texto não usa o estado para mudar ou impedir a classificação (regras.md, linha 31). Passa só se as três condições valerem |

## Partes do trabalho
| Parte | Entrada | Saída | Depende de | Critério próprio |
|---|---|---|---|---|
| 1 | R1 e registros T1 a T6 de `caso/regras.md` | Tabela com ID, estado, impacto, urgência, soma e prioridade | nada | As 6 linhas iguais a: T1 soma 5 `alta`; T2 soma 3 `media`; T3 soma 6 `alta`; T4 soma 2 `baixa`; T5 soma 4 `media`; T6 soma 5 `alta`. Conferir linha por linha, refazendo cada soma pela R1 |
| 2 | Tabela da parte 1 e Saída esperada | O texto em Markdown | parte 1 | Toda soma e prioridade do texto é igual à da tabela da parte 1, e o texto cumpre a Saída esperada e os critérios C1 a C3. Conferir comparando cada conta do texto com a tabela e aplicando C1 a C3. Passa só se as duas condições valerem |
