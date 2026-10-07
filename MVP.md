# MVP

## Pergunta do protótipo

> Segurar A e acertar as trocas com B é suficiente para tornar esta corrida curta divertida?

## Conteúdo obrigatório

- Uma pista reta com a composição da referência.
- Um carro jogável e um rival fixo.
- Quatro marchas.
- A para acelerar e B para subir marcha.
- Medidor de giro com faixa de troca e marcha grande.
- Contagem simples e largada automática.
- Animação simples das marcas da pista.
- Rival com posição vertical baseada na diferença de progresso.
- Resultado de vitória, derrota ou empate.
- Reinício com nova pressão de A.

## Ordem de construção

1. Montar a tela com painel, pista e dois carros.
2. Implementar os quatro estados e a leitura dos botões.
3. Implementar velocidade, giro e quatro marchas.
4. Adicionar distância, rival fixo e resultado.
5. Animar a pista e ajustar o timing das trocas.

## Critérios de aceitação

| Verificação | Resultado esperado |
|---|---|
| Tela no tamanho final | Giro, faixa de troca, marcha e dois carros são distinguíveis em 160 × 144 px |
| Contagem | Carros permanecem parados e em primeira marcha até a largada automática |
| Aceleração | Segurar A aumenta a velocidade; soltar A a reduz gradualmente |
| Troca | Cada troca exige soltar e pressionar B novamente e sobe exatamente uma marcha |
| Quarta marcha | Ao receber B, o carro mantém a quarta marcha e a velocidade atual |
| Timing | Troca dentro da faixa mantém velocidade; fora dela perde 10% |
| Disputa | Posição do rival corresponde a quem está à frente, permanecendo na área da pista |
| Chegada | Primeiro a atingir a distância vence; chegada dos dois na mesma atualização gera empate |
| Balanceamento | Trocas boas permitem vencer; várias trocas ruins permitem perder |
| Reinício | Nova pressão de A zera velocidade, distância e marcha para a próxima corrida |
| Leitura inicial | Um jogador consegue explicar A e B após ler a tela inicial |

Os critérios acima orientam a validação do protótipo durante a implementação.
