# Rival

## Papel

Um único rival fixo dá ao jogador uma referência clara de desempenho.

## Implementação prevista

Usar uma tabela curta de velocidade-alvo por intervalo de tempo. A velocidade do rival se aproxima desses alvos por incrementos inteiros, e sua distância é acumulada na mesma escala do jogador.

O perfil é idêntico em todas as tentativas.

## Leitura visual

O rival começa ao lado do jogador. Quando sua distância acumulada é maior, aparece mais acima na pista; quando é menor, aparece mais abaixo. Limitar esse deslocamento à área visível e manter o tamanho fixo do carro.

## Validação

Uma sequência de trocas boas deve permitir vencer. Várias trocas fora da faixa devem permitir que o rival vença. A dificuldade vem do timing do jogador.
