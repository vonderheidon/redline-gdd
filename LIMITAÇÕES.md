# Limitações e diretrizes técnicas

## Alvo e decisões pendentes

O alvo de design é uma tela de **160 × 144 px**, com controles digitais A e B e visual inspirado no Game Boy. A plataforma exata, a ferramenta de desenvolvimento e o formato de exportação dos assets precisam ser confirmados antes da implementação.

A compatibilidade com a plataforma escolhida será validada durante a implementação do protótipo.

## Arte e tela

- Quatro tons para o conjunto visual.
- Painel legível no tamanho final de 160 × 144 px.
- Cenário com elementos repetidos e poucas variações de animação.
- Dois carros de tamanho fixo.
- Preparar arte em grade de 8 × 8 px se o ambiente escolhido usar tiles.

## Lógica

Usar inteiros, tabelas curtas e atualização em intervalo fixo.

O medidor de giro é derivado da velocidade e da marcha. A comparação de progresso move apenas o rival dentro de limites visuais.

## Áudio

O áudio é opcional no primeiro protótipo. Se houver suporte simples, adicionar um som curto de troca e um de resultado. O feedback visual comunica todas as informações necessárias para jogar.

## Validação técnica

Depois de escolher o ambiente, confirmar como ele desenha o painel, anima a pista e posiciona os dois carros. Se usar sprites compostos ou tiles, verificar os limites reais da ferramenta e da plataforma antes de definir a divisão dos assets.

Validar a tela no tamanho final, a leitura de A segurado e B por nova pressão, a frequência das atualizações e o reinício completo. A aceitação de gameplay está em [[MVP]].
