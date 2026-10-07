# REDLINE GB — Game Design Document

> **Título provisório:** REDLINE GB  
> **Versão do GDD:** 0.2 — escopo simplificado  
> **Plataforma-alvo:** Game Boy; ambiente de desenvolvimento a confirmar  
> **Gênero:** Arrancada arcade / timing  
> **Perspectiva:** Vista traseira em pista reta  
> **Modo:** Um jogador contra um rival fixo

## Proposta

REDLINE GB é uma corrida curta em que o jogador segura **A para acelerar** e pressiona **B para subir marcha** no momento indicado pelo medidor de giro. São quatro marchas, uma pista e um carro jogável. O objetivo é chegar antes do rival.

A referência visual fornecida pelo autor orienta a composição: painel grande no topo, medidor de giro, indicações dos botões A e B, número da marcha à direita e dois carros na pista abaixo. A imagem é uma referência de aparência; os controles e as regras descritos aqui são decisões do projeto.

A sensação de velocidade vem da animação das marcas da pista. Os carros usam imagens de tamanho fixo, e a posição vertical do rival indica quem está à frente.

## Pilares

- Dois botões e uma regra de timing fácil de aprender.
- Giro e marcha legíveis durante toda a corrida.
- Cenário simples, poucos assets e animações reutilizáveis.
- Resultado direto e reinício rápido.

## Ciclo

**Início → contagem → aceleração e trocas → resultado → nova tentativa.**

Na tela inicial, A inicia a contagem. A largada é automática ao final da contagem, com ambos os carros parados e em primeira marcha. A aceleração fica habilitada a partir do sinal de largada.

Durante a corrida, segurar A faz o carro ganhar velocidade. B sobe uma marcha por pressão, até a quarta. Uma troca na faixa indicada preserva melhor a aceleração; trocar cedo ou tarde custa desempenho, mas a corrida continua.

## Vitória e derrota

Vence quem atingir primeiro a distância final, medida em unidades internas. Se ambos chegarem na mesma atualização, o resultado é empate. O resultado mostra **VENCEU**, **PERDEU** ou **EMPATE** e permite tentar novamente com A.

## Escopo e fonte de verdade

Este README define a proposta e [[MVP]] define o conteúdo e a aceitação da primeira versão. [[MECANICAS]], [[CONTROLES]] e [[HUD]] detalham esse mesmo escopo.

A primeira entrega é um protótipo de arrancada arcade compatível com a simplicidade da referência.
