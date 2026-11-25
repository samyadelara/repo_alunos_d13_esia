# Passo 1: critérios escritos antes da IA (demanda B)

Demanda B: "Preciso explicar como a prioridade funciona".
Escritos pela aluna antes da Rodada 1, com revisão do tutor (Claude Code). Não houve aula com o professor.

## Critérios

| ID | Dada esta entrada | Deve acontecer | Como vou conferir |
|---|---|---|---|
| C1 (normal) | T4: impacto 1, urgência 1 | O texto mostra a soma 1 + 1 = 2 e classifica como `baixa` | Refazer a soma pela R1: soma 2 → `baixa` |
| C2 (fronteira) | T5: impacto 2, urgência 2; T6: impacto 2, urgência 3 | O texto mostra 2 + 2 = 4 → `media` e 2 + 3 = 5 → `alta`, deixando claro que a mudança de faixa acontece entre 4 e 5 | Refazer as duas somas pela R1. Passa só se as duas classificações estiverem certas |
| C3 (exclusão) | T2 (Laboratório, impacto 1, urgência 2) e T3 (Oficina, `fechado`, impacto 3, urgência 3) | O texto classifica T2 como `media` (1 + 2 = 3) e T3 como `alta` (3 + 3 = 6), sem dizer que departamento ou estado muda ou impede a classificação | Refazer as somas pela R1. Procurar menção a departamento ou estado como fator de prioridade. Fonte: regras.md, linha 31. Passa só se as duas classificações estiverem certas e não houver essa menção |

## Limites e hipóteses

- Limite: o texto não define ordem nem prazo de atendimento.
- Hipótese (não confirmada pela demanda): a pessoa nova é do time que atende chamados.

## Escolhas e motivos

- C1 usa T4 para cobrir a faixa `baixa`, já que o C2 cobre `media` e `alta`.
- C2 usa dois registros para mostrar os dois lados da fronteira. Assim, um texto que diga "soma ≥ 4 é alta" falha no T5.
- C3 testa a exclusão de filtro por departamento e estado (regras.md, linha 31). Primeira versão descartada: "o texto menciona os seis casos sem filtro", porque criava um requisito novo e era ambígua sobre estado.
