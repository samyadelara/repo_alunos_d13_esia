# Rodada 1: resposta da IA (demanda B)

Origem: execução real, em sessão separada do Claude Code, com o pedido de partida abaixo. A sessão não viu os critérios do passo 1. Texto copiado sem alteração.

Pedido de partida:

```text
Leia caso/regras.md e a demanda B de caso/demandas.md. Proponha uma história de usuário e três critérios observáveis. Separe fatos confirmados, sugestões suas e dúvidas. Não acrescente regra como se estivesse aprovada. Não altere arquivos.
```

## Resposta

História de usuário (proposta)
Como pessoa nova na equipe que atende chamados da Oficina e do Laboratório,
quero uma explicação de como a prioridade de um chamado é definida,
para conseguir classificar um chamado sozinha a partir do impacto e da urgência.

Critérios observáveis
A regra está completa. A explicação diz que impacto e urgência são inteiros de 1 a 3 e que eles são somados. Diz também em que faixa cai cada soma: 5 ou mais é alta, 3 ou 4 é media e 2 é baixa. Para conferir, basta ver que toda soma possível de 2 a 6 tem uma faixa e que não há faixa a mais.
Há um exemplo conferível para cada faixa. A explicação mostra pelo menos um caso de cada prioridade, e qualquer pessoa consegue refazer a conta. Exemplos tirados dos registros do caso:
T4: 1 + 1 = 2, prioridade baixa
T5: 2 + 2 = 4, prioridade media
T1: 3 + 2 = 5, prioridade alta
Só aparece o que está em R1. O texto não apresenta como regra nada além de R1: nada de prazo, e-mail, administrador, filtro por departamento, nem estado mudando a prioridade. O valor de saída aparece como media, sem acento. Para conferir, basta procurar esses termos no texto.
Fatos confirmados (vêm de regras.md)
R1 define a prioridade pela soma de impacto e urgência, com três faixas.
R4 exige que a documentação respeite R1, R2 e R3.
As entradas são válidas, então não é preciso tratar valores fora de 1 a 3.
media é escrito sem acento na saída.
Quando a tarefa é só classificar prioridade, não se acrescenta filtro por departamento.
As contas de T1, T4 e T5 acima seguem diretamente de R1.
Sugestões minhas (não são regras aprovadas)
Incluir uma tabela com as somas de 2 a 6 e a prioridade de cada uma, para consulta rápida.
Incluir um exemplo de limite, como 1 + 2 = 3 (media), já que as fronteiras confundem com mais facilidade.
Mencionar de passagem que visibilidade (R3) e chamados ativos (R2) são assuntos separados, para evitar confusão.
Dúvidas para quem pediu
Quem é exatamente a pessoa nova? A história supõe que ela atende chamados, mas isso não foi confirmado.
Em que formato será a explicação: texto escrito, conversa ou documento guardado em algum lugar?
É preciso explicar por que as faixas são essas? O caso não traz essa justificativa.
A explicação deve tocar em R2 e R3, ou ficar só em R1?
Basta a explicação, ou a pessoa nova também deve conseguir calcular sozinha, com algum exercício para verificar?
