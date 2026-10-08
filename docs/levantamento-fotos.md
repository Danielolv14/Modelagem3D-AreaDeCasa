---
titulo: Levantamento pelas fotos — área de serviço
criado: 2026-10-08
tags:
  - projeto/modelagem3d
  - casa/area-de-servico
---

# Levantamento pelas fotos

Leitura de 5 fotos tiradas em 2026-10-08. As fotos não ficam no repositório.

## Formato

Corredor estreito e comprido: a janela fica num lado curto, e uma parede só de azulejo
fica no outro.

## Croqui (interpretação, a confirmar)

```
                           PAREDE DA PORTA
          (interfone · interruptor · quadro de luz · varal sanfonado)
         ┌──[ PORTA ]─────────────────────────────────────────┐
         │    ╲ abre p/ dentro?                    [sapateira] │
  PAREDE │                                                    │ PAREDE
   CEGA  │                                         [lixeira]  │ DA JANELA
         │                                                    │ (janela de
         │  ?  [forno+suporte] [máquina Consul]    [tanque]   │  correr)
         └──?─────────────────────────────────────────────────┘
                         PAREDE DOS ARMÁRIOS
                  (armários aéreos de ponta a ponta)

   ? = possível passagem para a cozinha (não aparece em nenhuma foto)
```

## O que tem em cada parede

| Parede | Itens |
|---|---|
| **Parede da porta** (comprida) | Porta de madeira encostada no canto com a parede cega, com duas fechaduras. Ao lado da porta, em direção à janela: interfone (alto) e interruptor (baixo). Depois, quadro de disjuntores e varal sanfonado de parede seguindo em direção à janela. Ganchos com rodo e vassoura. Sapateira no canto com a janela. |
| **Parede dos armários** (comprida) | Armários aéreos brancos de ponta a ponta. Embaixo, partindo da parede cega: forno elétrico sobre suporte aramado, máquina **Consul 9 kg de tampa superior** e tanque no canto da janela, com torneira e ponto de água da máquina. |
| **Parede da janela** | Janela de correr com 2 folhas. Varal tubular de parede ao lado da janela, do lado dos armários. Lixeira embaixo. |
| **Parede cega** | Só azulejo. Escada encostada perto da porta. |
| **Teto** | Ponto de luz mais ou menos no centro (bocal sem luminária). |

## Observações importantes para a simulação

- **A porta de madeira provavelmente abre para dentro da área.** As dobradiças aparecem do lado da área, no lado da parede cega. A área que a porta varre ao abrir precisa ficar livre.
- **O quadro de disjuntores precisa continuar acessível.** Nenhum equipamento pode ficar na frente dele.
- O corredor entre a frente da máquina/forno e a parede da porta é o espaço de circulação crítico.

## Respostas e conclusões

- **Porta de madeira:** dá para o **corredor do prédio** (resposta do usuário em 2026-10-08).
- **Passagem da cozinha:** o usuário veio da cozinha ao tirar as fotos 1 e 2. Pelo ângulo das fotos, a passagem fica **na parede dos armários, no canto da parede cega**, logo antes do forno. Largura estimada em 80 cm, ainda **a confirmar**.
- **Orientação:** quem olha da cozinha para a janela tem os armários à **direita**. De frente para a bancada, a janela fica à **esquerda**.
- A porta do prédio abre para dentro, e a área que ela varre fica em frente à passagem da cozinha. Por isso não bate na bancada nova, que começa depois da passagem.
- **Sapateira e lixeira** (canto da janela) não cabem na frente da bancada nova: sobrariam só ~15 cm para passar. Vão precisar de outro lugar.
