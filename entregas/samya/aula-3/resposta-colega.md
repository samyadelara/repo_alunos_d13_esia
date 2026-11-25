# Resposta da execução: especificação v1

## Origem
- Execução: sessão separada do Claude Code, que leu só `especificacao-v1.md` e as entradas listadas nela. Data: 23/11/2026.
- Conferência: inspeção manual feita pela própria autora, sem colega disponível. Conferiu só pelo que está escrito na v1.

## Pedido usado na execução
```text
Leia somente entregas/samya/aula-3/especificacao-v1.md e os arquivos que ela lista em "Entradas e fonte da verdade". Não leia rodada1-ia.md nem os arquivos notas-*. Produza apenas o texto que a especificação pede. Se precisou supor algo que não estava escrito, liste depois do texto. Não altere arquivos.
```

## Texto gerado (sem alteração)

Como a prioridade de um chamado é definida

A prioridade depende só de dois números: impacto e urgência. Cada um é um inteiro de 1 a 3. Some os dois e veja a faixa:

soma 2: baixa;
soma 3 ou 4: media;
soma 5 ou mais: alta.
Exemplos:

T4: impacto 1 + urgência 1 = 2 → baixa.
T5: impacto 2 + urgência 2 = 4 → media.
T6: impacto 2 + urgência 3 = 5 → alta. A faixa muda entre 4 e 5: soma 4 ainda é media, e soma 5 já é alta.
T3: impacto 3 + urgência 3 = 6 → alta.
Estado e departamento não entram no cálculo da prioridade.

Palavras: 115 na contagem da autora. O executor declarou "cerca de 100" e o tutor contou cerca de 101 sem os símbolos (+, =, →) e cerca de 113 com eles. Todas as contagens ficam abaixo de 120, mas a v1 não diz como contar.

## Suposições declaradas pelo executor (sem alteração)

- Contagem de palavras: contei o título, os números e os IDs (T4, T5...) como palavras. Os símbolos (+, =, →) ficaram de fora. Assim o texto fica com cerca de 100 palavras. A especificação não diz como contar.
- Ordem: como a especificação deixa a ordem em aberto, escolhi esta: regra, faixas, exemplos e a frase sobre estado e departamento. Nos exemplos, segui a ordem em que a especificação lista os casos: T4, T5, T6 e T3.
- Estado do T3: não escrevi que o T3 está fechado. Citar o estado ao lado da conta poderia dar a impressão de que ele importa para a prioridade (critério C3). A única menção a estado é a frase final, que a especificação pede.
- "Soma 5 ou mais": a R1 diz "maior ou igual a 5". Mantive a forma da especificação, que tem o mesmo sentido. Com inteiros de 1 a 3, a soma máxima é 6.
- Formato: usei Markdown, com lista e media em código. A especificação não define o formato do texto.
- Não criei nem alterei arquivos.

## Conferência dos critérios
| ID | Resultado | Evidência no texto | Observação |
|---|---|---|---|
| C1 | passou | "T4: impacto 1 + urgência 1 = 2 → baixa." | Conta refeita pela R1 |
| C2 | passou | "T5: ... = 4 → media." e "T6: ... = 5 → alta. A faixa muda entre 4 e 5" | As duas contas estão certas pela R1, e a fronteira está explícita |
| C3 | passou, com observação | "T3: impacto 3 + urgência 3 = 6 → alta." e "Estado e departamento não entram no cálculo da prioridade." | Pelo escrito, passa: a conta está certa e o estado não aparece como fator. Mas o texto não diz que o T3 está `fechado`, então não mostra que um chamado fechado continua com prioridade. O executor omitiu o estado de propósito. O critério não exige mostrar o estado, então não confere a intenção |

## Itens da Saída esperada
| Item | Presente? | Evidência |
|---|---|---|
| até 120 palavras | sim | 115 pela contagem da autora (ver nota acima) |
| regra (1 a 3, somados) | sim | "Cada um é um inteiro de 1 a 3. Some os dois" |
| três faixas | sim | "soma 2: baixa; soma 3 ou 4: media; soma 5 ou mais: alta" |
| contas de T4, T5, T6 e T3 | sim | quatro linhas de exemplo |
| frase: estado e departamento não entram no cálculo | sim | última frase |
| sem prazo nem ordem de atendimento | sim | nenhuma menção |
| `media` sem acento | sim | "media" nas faixas e no T5 |

## O que não deu para conferir só pelo escrito
- C3: o critério não exige que o texto mostre o estado `fechado` do T3. Por isso, não dá para conferir se o texto ensina que o estado não impede a classificação. Candidato a critério reescrito.
- Contagem de palavras: a v1 não define o método de contagem (título, números e símbolos).
- Ordem e formato do texto não estão definidos na v1. O executor escolheu.
