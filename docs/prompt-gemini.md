---
titulo: Prompt para o Gemini — levantamento de medidas
criado: 2026-10-08
tags:
  - projeto/modelagem3d
  - prompt
---

# Prompt para o Gemini

Colar na **mesma conversa** do Gemini em que estão o planejamento e as medidas. Depois,
copiar a resposta inteira e mandar para o Claude.

```text
Preciso que você organize TUDO o que conversamos aqui sobre a área de serviço e os equipamentos. Vou passar essas informações para outra ferramenta, que vai montar uma simulação 3D com as medidas reais. A simulação vai mostrar para minha mãe se os equipamentos cabem, então precisão importa mais do que preencher tudo.

REGRAS
1. Use somente informações que aparecem nesta conversa. Não invente nem chute medidas.
2. Se uma informação não foi dita, escreva NÃO INFORMADO.
3. Se o valor foi sugerido ou estimado por você (e não medido por mim), escreva (ESTIMADO) ao lado.
4. Se uma medida mudou ao longo da conversa, use a mais recente e coloque a antiga entre parênteses.
5. Todas as medidas em centímetros.
6. Responda em UM ÚNICO bloco de código, seguindo exatamente o modelo abaixo. Repita os blocos marcados com (repetir) quantas vezes precisar. Se houver informação útil que não cabe no modelo, acrescente campos.

NOMES DAS PAREDES (use sempre estes nomes):
- PAREDE DA JANELA: a do fundo, onde fica a janela.
- PAREDE CEGA: a oposta à janela, só com azulejo.
- PAREDE DA PORTA: parede comprida onde ficam a porta de madeira, o interfone, o interruptor, o quadro de luz e o varal sanfonado.
- PAREDE DOS ARMÁRIOS: parede comprida oposta, com os armários aéreos, o forno, a máquina de lavar e o tanque.

COMO INDICAR POSIÇÃO:
- Itens na PAREDE DA PORTA ou na PAREDE DOS ARMÁRIOS: distância da PAREDE CEGA até a borda mais próxima do item.
- Itens na PAREDE DA JANELA ou na PAREDE CEGA: distância da PAREDE DOS ARMÁRIOS até a borda mais próxima do item.
- Altura: sempre do chão.

MODELO:

=== CÔMODO ===
comprimento da PAREDE DA PORTA:
comprimento da PAREDE DOS ARMÁRIOS:
largura da PAREDE DA JANELA:
largura da PAREDE CEGA:
pé-direito (altura do teto):
diagonais do piso:
pilar / viga / rebaixo / degrau / desnível:
ralo do piso (posição):
tamanho do piso e do azulejo:

=== PORTA DE MADEIRA ===
dá acesso a (corredor do prédio / cozinha / outro):
distância da PAREDE CEGA até o batente:
largura da folha:
largura total com batente:
altura:
abre para (dentro da área / fora):
lado da dobradiça:

=== ACESSO À COZINHA ===
onde fica:
tipo (porta / vão aberto):
largura:
altura:

=== JANELA ===
distância da PAREDE DOS ARMÁRIOS:
largura:
altura:
altura do peitoril:
tipo (correr / basculante / outro):

=== ARMÁRIOS AÉREOS ===
comprimento total:
profundidade:
altura do armário:
altura do chão até a base do armário:
quantidade de portas:

=== TANQUE ===
largura:
profundidade:
altura da borda:
distância da PAREDE DA JANELA:
altura da torneira:

=== MÁQUINA DE LAVAR ATUAL ===
marca / modelo:
largura x altura x profundidade:
posição:
fica / sai / muda de lugar:

=== FORNO ELÉTRICO E SUPORTE ===
forno (largura x altura x profundidade):
suporte (largura x altura x profundidade):
posição:
fica / sai / muda de lugar:

=== OUTROS ITENS EXISTENTES (repetir) ===
(varal sanfonado, varal tubular da janela, sapateira, lixeira, escada, etc.)
nome:
largura x altura x profundidade:
posição:
fica / sai / muda de lugar:

=== PONTOS ELÉTRICOS E HIDRÁULICOS ===
(um por linha: tipo | parede | distância | altura do chão | observação)
tomadas (com voltagem 127 V / 220 V):
ponto de água da máquina:
esgoto da máquina:
quadro de luz:
interfone:
interruptor:
ponto de luz do teto:

=== EQUIPAMENTOS NOVOS (repetir) ===
nome:
marca / modelo:
link da ficha técnica:
largura x altura x profundidade:
tipo de abertura (porta frontal / tampa em cima / outro):
espaço ocupado com a porta ou tampa aberta:
folgas exigidas pelo manual (atrás / laterais / em cima):
voltagem / potência:
precisa de água / esgoto / saída de ar:
pode empilhar ou pendurar:
posição pretendida:

=== LAYOUTS E IDEIAS JÁ DISCUTIDOS (repetir) ===
nome da opção:
o que fica onde:
prós e contras levantados:

=== DECISÕES JÁ TOMADAS ===

=== RESTRIÇÕES E PREFERÊNCIAS ===
o que não pode mudar de lugar:
o que pode sair da área:
espaço mínimo de passagem desejado:
outras:

=== PENDÊNCIAS ===
(medidas que ainda faltam e decisões em aberto)
```
