# Evidências: especificação v1 e v2

Demanda B: "Preciso explicar como a prioridade funciona". Caso Fila Clara.

Como foi feito: nos dois casos, a execução foi feita por uma sessão separada do Claude Code, que leu só a especificação e as entradas listadas nela. A conferência foi uma inspeção manual da própria autora, sem colega disponível, olhando só para o que está escrito na especificação.

Por que não houve colega: não havia colega disponível para executar a especificação. Para substituir a devolutiva, a autora fez o exercício simulando o papel de colega numa sessão separada. Essa sessão não teve acesso às notas nem ao raciocínio da especificação, só ao que estava escrito nela. Por isso, a devolutiva da seção 1 é uma simulação, e não uma execução feita por outra pessoa.

## 1. Devolutiva da v1

Fonte completa: `aula-3/resposta-colega.md` (execução de 23/11/2026).

| Critério da v1 | Resultado | Observação |
|---|---|---|
| C1 (T4 → `baixa`) | passou | Conta refeita pela R1 |
| C2 (T5 → `media`, T6 → `alta`) | passou | Fronteira 4 e 5 explícita |
| C3 (T3 `fechado` → `alta`) | passou, com observação | O texto nunca diz que o T3 está `fechado`. O executor omitiu o estado de propósito. O critério não exigia mostrar o estado, então não conferia a intenção |

O que não deu para conferir só pelo escrito na v1:
- C3: não exige mostrar o estado, então não confere se o texto ensina que um chamado `fechado` continua sendo classificado.
- Contagem de palavras: a v1 não diz como contar. Contagens: autora 115, executor cerca de 100, tutor cerca de 101 a 113.
- Ordem e formato do texto não estão definidos. O executor escolheu.

## 2. Execução da v2

Data: 23/11/2026.

Pedido usado:
```text
Leia somente entregas/samya/atividade-1/especificacao-v2.md e os arquivos que ela lista em "Entradas e fonte da verdade". Não leia outros arquivos de entregas/.
Execute as duas partes descritas em "Partes do trabalho", na ordem:
1. Mostre a tabela da parte 1.
2. Mostre o texto da parte 2, feito a partir dessa tabela.
Se precisou supor algo que não estava escrito, liste depois. Não altere arquivos.
```

### Saída da parte 1 (sem alteração)

| ID | Estado | Impacto | Urgência | Soma | Prioridade |
|---|---|---:|---:|---:|---|
| T1 | aberto | 3 | 2 | 5 | `alta` |
| T2 | em_andamento | 1 | 2 | 3 | `media` |
| T3 | fechado | 3 | 3 | 6 | `alta` |
| T4 | em_andamento | 1 | 1 | 2 | `baixa` |
| T5 | aberto | 2 | 2 | 4 | `media` |
| T6 | aberto | 2 | 3 | 5 | `alta` |

### Saída da parte 2 (sem alteração)

```markdown
# Como a prioridade é definida

Cada chamado tem impacto e urgência, dois números inteiros de 1 a 3. Para achar a prioridade, some os dois.

Faixas:
- soma 2 → `baixa`;
- soma 3 ou 4 → `media`;
- soma 5 ou mais → `alta`.

Exemplos:
- T4: 1 + 1 = 2 → `baixa`.
- T5: 2 + 2 = 4 → `media`.
- T6 (`aberto`): 2 + 3 = 5 → `alta`.
- T3 (`fechado`): 3 + 3 = 6 → `alta`.

Repare que a faixa muda entre 4 e 5: soma 4 ainda é `media`; soma 5 já é `alta`.

Estado e departamento não entram no cálculo da prioridade.
```

### Suposições declaradas pelo executor (resumo)

1. Contou os números e as palavras dentro de crases (`media`, `aberto`), porque só a marcação não conta. Contagem à mão: cerca de 80.
2. Colocou a frase "Repare que a faixa muda entre 4 e 5" depois dos exemplos e antes da frase final. A Saída esperada não diz onde ela entra. Ela está no texto para cumprir o "deixando claro" do C2.
3. Mostrou o estado entre parênteses, logo depois do ID. A especificação só pede "ao lado da conta".
4. Não explicou por que as faixas são essas: a dúvida continua aberta.
5. Não usou a hipótese da pessoa nova no texto e não fala de filtro por departamento.

O executor também se autoavaliou e marcou tudo como "passou". Essa autoavaliação não conta como conferência.

## 3. Conferência da v2 (inspeção manual da autora)

| Item | Resultado | Como conferi |
|---|---|---|
| Parte 1 | passou | Refiz as 6 somas pela R1 e conferi a ordem e as colunas da tabela. Todas iguais ao critério da parte 1 |
| Parte 2 | passou | As contas do texto são iguais às da tabela da parte 1. O texto está no formato pedido (Markdown) e cumpre a Saída esperada e C1 a C3 |
| C1 (normal) | passou | "T4: 1 + 1 = 2 → `baixa`". Conta refeita pela R1 |
| C2 (fronteira) | passou | "T5: 2 + 2 = 4 → `media`" e "T6 (`aberto`): 2 + 3 = 5 → `alta`", mais a frase "a faixa muda entre 4 e 5". Contas refeitas pela R1 |
| C3 (exclusão) | passou | "T6 (`aberto`): 2 + 3 = 5 → `alta`" e "T3 (`fechado`): 3 + 3 = 6 → `alta`". O estado aparece nos dois, as somas estão certas e o estado não é usado no cálculo |
| Até 120 palavras | passou | 81 palavras pela regra da v2. Contei as palavras dentro de crases, que são palavras do texto e não marcação |
| `media` sem acento, sem prazo, sem ordem de atendimento | passou | Nenhuma ocorrência em contrário |

## 4. Observações para uma próxima versão

- A Saída esperada lista 4 itens em ordem, mas não diz se pode haver frase fora deles. O executor colocou a frase da fronteira entre os itens 3 e 4.
- A regra de contagem não diz explicitamente que palavras dentro de marcação (crases) contam. A autora e o executor contaram, e as contagens ficaram próximas (81 e cerca de 80).
