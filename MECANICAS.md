# Mecânicas

## Estados

| Estado | Comportamento |
|---|---|
| `INICIO` | Exibe o convite para começar com A |
| `CONTAGEM` | Mostra 3, 2, 1; carros parados e entradas de corrida ignoradas |
| `CORRIDA` | Largada automática, aceleração e trocas habilitadas |
| `RESULTADO` | Congela a corrida, mostra o vencedor e aguarda nova pressão de A |

Toda nova corrida começa com velocidade e distância zeradas e primeira marcha para os dois carros.

## Modelo arcade

Usar poucos valores inteiros:

| Valor | Função |
|---|---|
| `marcha` | Número de 1 a 4 |
| `velocidade` | Determina avanço e ritmo da pista |
| `giro` | Valor de 0 a 100 calculado a partir da velocidade e da marcha |
| `distancia_jogador` | Progresso acumulado do jogador |
| `distancia_rival` | Progresso acumulado do rival |

Cada marcha tem um limite de velocidade e um ganho de aceleração definidos em uma tabela pequena. Com A segurado, a velocidade aumenta até o limite da marcha. Com A solto, diminui gradualmente até zero. A distância avança conforme a velocidade a cada atualização.

O giro representa a velocidade em relação ao limite da marcha atual.

## Trocas

Faixa inicial de troca boa: **75 a 90** no medidor de 0 a 100. Esses valores são parâmetros ajustáveis de balanceamento na escala interna do jogo.

Ao receber uma nova pressão de B nas marchas 1 a 3:

1. Avaliar o giro antes da troca.
2. Subir uma marcha.
3. Dentro da faixa boa, manter a velocidade.
4. Fora da faixa boa, reduzir a velocidade em 10%, usando cálculo inteiro.
5. Recalcular o giro para a nova marcha.

No limite da marcha, a velocidade para de crescer até a próxima troca. Na quarta marcha, o jogador apenas mantém a aceleração. A quarta marcha é a marcha final, e sua velocidade se estabiliza no limite.

## Rival e chegada

O rival usa uma sequência fixa de aceleração, com valores definidos por tempo de corrida. O mesmo perfil de aceleração é usado em todas as tentativas.

Ambos acumulam distância na mesma escala. Quando um deles atingir a distância final, comparar os dois progressos naquela atualização: apenas o jogador chegou = vitória; apenas o rival chegou = derrota; ambos chegaram = empate.

A distância final é um parâmetro interno escolhido para produzir uma corrida curta. O progresso é medido em unidades internas do jogo.

## Balanceamento inicial

A execução com trocas boas deve vencer o rival. Uma execução com várias trocas ruins deve perder. Ajustar as tabelas de aceleração e a distância final para que essa diferença seja perceptível.

## Resultado e repetição

Mostrar apenas o resultado e a instrução **A: NOVAMENTE**. Ao reiniciar, limpar todos os valores da corrida anterior.
