# Especificação curta

Responsável: Samya · Versão: v1 · Data: 23/11/2026

Demanda B (`caso/demandas.md`): "Preciso explicar como a prioridade funciona".

## Necessidade e objetivo
Uma pessoa nova no time que atende chamados precisa de um texto curto que explique como a prioridade de um chamado é definida, para entender a classificação a partir do impacto e da urgência.

## Entradas e fonte da verdade
- `caso/regras.md`: R1 (prioridade), linha 12 (`media` sem acento; não existe regra de prazo de atendimento) e linha 31 (não acrescentar filtro quando a tarefa é só classificar prioridade).
- `caso/decisoes-confirmadas.md`, decisão da demanda B.
- Registros de `caso/regras.md` usados nos critérios: T3, T4, T5 e T6.

## Limites e dúvidas
- Confirmado (decisão B): texto de até 120 palavras; não promete prazo de atendimento.
- Confirmado (R1): a prioridade depende só de impacto e urgência. `media` é escrito sem acento (regras.md, linha 12).
- Limite: o texto não define ordem de atendimento.
- Hipótese: a pessoa nova atende chamados do próprio departamento. A demanda e a decisão B não dizem quem é a pessoa.
- Dúvida: é preciso explicar por que as faixas são essas? O caso não traz essa justificativa.

## Saída esperada
Texto em português, de até 120 palavras, com:
- a regra: impacto e urgência são inteiros de 1 a 3 e são somados;
- as três faixas: soma 2 → `baixa`; soma 3 ou 4 → `media`; soma 5 ou mais → `alta`;
- as contas de T4, T5, T6 e T3, com a soma e a prioridade de cada um;
- uma frase dizendo que estado e departamento não entram no cálculo da prioridade.

A ordem dos itens no texto não está definida nesta versão.

## Critérios de aceite
| ID | Dada esta entrada | Deve acontecer | Como vou conferir |
|---|---|---|---|
| C1 (normal) | T4: impacto 1, urgência 1 | O texto mostra 1 + 1 = 2 → `baixa` | Refazer a soma pela R1: soma 2 → `baixa` |
| C2 (fronteira) | T5: impacto 2, urgência 2; T6: impacto 2, urgência 3 | O texto mostra 2 + 2 = 4 → `media` e 2 + 3 = 5 → `alta`, deixando claro que a faixa muda entre 4 e 5 | Refazer as duas somas pela R1 e conferir com a decisão B (exemplos de soma 4 e 5). Passa só se as duas classificações estiverem certas |
| C3 (exclusão) | T3: estado `fechado`, impacto 3, urgência 3 | O texto mostra 3 + 3 = 6 → `alta`, sem dizer que o estado muda ou impede a classificação | Refazer a soma pela R1. Procurar no texto menção a estado como fator de prioridade (regras.md, linha 31). Passa só se a classificação estiver certa e não houver essa menção |

## Partes do trabalho
Opcional na prática da aula 3. Não preenchido nesta versão.
