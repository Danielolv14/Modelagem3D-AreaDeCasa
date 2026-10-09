---
titulo: Plano — Simulação 3D da área de serviço
criado: 2026-10-08
status: versão 1 publicada
tags:
  - projeto/modelagem3d
  - casa/area-de-servico
  - threejs
---

# Plano — Simulação 3D da área de serviço

## Objetivo

Montar uma **simulação 3D interativa** da área de serviço com as medidas reais,
para a mãe ver no celular se os equipamentos novos cabem, como fica a circulação
e se as portas abrem sem bater em nada.

O que importa é ser **fiel às medidas** e **fácil de usar**. Não precisa ser realista.

---

## Tecnologia escolhida

**Página web 3D feita com [Three.js](https://threejs.org/) (JavaScript)**, publicada
por link (GitHub Pages).

| Opção | Por que sim / por que não |
|---|---|
| **Three.js (escolhida)** | Gerada por código a partir das medidas: mudou um número, o modelo se atualiza. Abre no navegador do celular por um link, sem instalar nada. É interativa (girar, zoom, trocar cenário) e a hospedagem é gratuita. |
| SketchUp / Sweet Home 3D / Planner 5D | Tudo é feito à mão em programa gráfico, então eu não consigo automatizar. Para ver, a mãe precisaria do app ou do arquivo. |
| Blender | Gera imagens bonitas, mas estáticas, e dá muito trabalho para ajustar medidas. Fica de opção para renders finais, se um dia quiser. |

### Estrutura do projeto

O usuário pediu algo mais simples, então a página virou **um arquivo só**:

```
index.html   → página inteira (Three.js 0.160.0 via jsDelivr, versão fixa)
               no topo do script: PADRAO + montarMedidas() com TODAS as medidas, em cm
```

Regra principal: **nenhuma medida fica espalhada pelo código**. Tudo sai de `PADRAO` e
`montarMedidas()`, no começo do script do `index.html`. A cena inteira é remontada
(`construir()`) sempre que uma medida muda no painel "E se…?".

Publicação: Vercel, projeto `area-de-servico-3d`, a partir desta branch. Para atualizar o
link depois de mudar o código, é preciso fazer uma nova implantação.

### O que a página vai ter (pensado para a mãe)

1. **Visão 3D giratória**: arrastar o dedo gira, pinça dá zoom.
2. **Visão "em pé na porta"**: câmera na altura dos olhos (~1,60 m), como quem entra na área.
3. **Planta vista de cima** com as cotas em cm.
4. **Botões de cenário**: "Como está hoje", "Opção A", "Opção B"…
5. **Equipamentos coloridos com rótulo** (nome + L × A × P).
6. **Zonas de folga translúcidas**: abertura da porta da lavadora/secadora, ventilação
   atrás e nas laterais, espaço para a pessoa ficar em pé e circular.
7. **Aviso automático** para cada equipamento:
   - 🟢 *cabe, sobram X cm*
   - 🟡 *cabe, mas tampa tomada / torneira / porta*
   - 🔴 *não cabe, faltam X cm*

---

## Etapas

| Fase | O que é feito | Quem |
|---|---|---|
| **0. Coleta** | Conversa do Gemini, medidas, fotos e croqui (ver checklist abaixo) | Você |
| **1. Cômodo vazio** | Paredes, porta, janela, tanque e pontos fixos. Validação comparando screenshots do modelo com as fotos, no mesmo ângulo | Claude |
| **2. Equipamentos** | Caixas com as medidas exatas da ficha técnica de cada modelo + zonas de folga | Claude |
| **3. Cenários + verificação** | Layouts alternativos e avisos "cabe / não cabe" | Claude |
| **4. Publicação** | Link do GitHub Pages, testado na tela de celular | Claude + você (1 clique para ativar o Pages) |
| **5. Acabamento (opcional)** | Cores de piso e azulejo parecidas com as fotos, modelos 3D mais realistas (.glb), imagens prontas para mandar no WhatsApp | Claude |

> Dá para validar aqui mesmo: gero screenshots do modelo com navegador headless
> (Playwright/Chromium) e comparo com as fotos antes de te mandar.

---

## Checklist de informações necessárias

### A. Conversa do Gemini
- [ ] **Colar o texto** da conversa aqui no chat. É o jeito mais garantido: links de
  compartilhamento do Gemini podem não abrir do meu lado.

### B. Cômodo
- [ ] **Comprimento e largura** do piso. Medir rente ao chão **e** a ~1 m de altura, porque parede nem sempre é reta.
- [ ] **As duas diagonais** do piso, para saber se o cômodo está no esquadro.
- [ ] **Pé-direito** (altura até o teto).
- [ ] Tem **pilar, viga, rebaixo de teto, degrau, desnível ou recorte**? Onde e de que tamanho?
- [ ] **Croqui à mão, visto de cima**, com as paredes numeradas (ex.: Parede 1 = a da porta de entrada, depois em sentido horário). Pode ser feio, só precisa estar legível.

### C. Aberturas (para cada porta e janela)
- [ ] Em qual parede fica e a que distância do canto.
- [ ] Largura e altura. Para janela, também a altura do peitoril (do chão até a base).
- [ ] Tipo (abrir, correr, basculante, sanfona).
- [ ] Sentido de abertura (para dentro ou para fora, dobradiça à esquerda ou à direita).

### D. Elementos fixos e pontos de instalação
Para cada um: **parede**, **distância do canto** e **altura do chão**.
- [ ] Tanque, máquina atual, armários, prateleiras, varal (de teto ou de parede), aquecedor.
- [ ] **Tomadas**, com a voltagem (127 V ou 220 V).
- [ ] **Torneiras e pontos de água**, **ralo e esgoto**, registro, quadro de disjuntores, gás (se houver).

### E. Equipamentos novos
- [ ] **Marca e modelo exatos** de cada um (eu procuro a ficha técnica oficial). Sem modelo definido, mandar **largura × altura × profundidade**.
- [ ] Tipo de abertura (porta frontal, tampa em cima, gaveta).
- [ ] Voltagem.
- [ ] Se vai **empilhar** (ex.: secadora sobre lavadora) ou **pendurar** na parede.
- [ ] Onde a família *gostaria* de colocar, se já tiver ideia.

### F. Restrições e preferências
- [ ] O que **pode** mudar de lugar e o que **não pode** (ex.: tanque fixo).
- [ ] Espaço mínimo de passagem que a mãe considera confortável.
- [ ] Algum uso específico (estender roupa, guardar vassoura, tábua de passar…).

### G. Fotos (como tirar)
- [ ] **Uma foto de cada canto**, pegando o máximo do cômodo, em pé, com o celular na altura do peito.
- [ ] **Uma foto de frente para cada parede.**
- [ ] **Foto da porta olhando para dentro**, que é o ângulo de quem entra. Vai virar a câmera inicial do modelo.
- [ ] **Close** das tomadas, torneiras e ralo.
- [ ] Se der, **trena esticada aparecendo** em algumas fotos.
- [ ] Boa luz. Mandar uma no zoom normal (1x) e uma na grande-angular (0,5x), porque a 0,5x distorce mas mostra tudo.

> Medidas em **centímetros**, de preferência. Se uma medida estiver em dúvida, marcar
> com "?" e eu destaco no modelo como "a confirmar".

---

## Folgas típicas (a confirmar no manual de cada modelo)

| Item | Folga usual |
|---|---|
| Ventilação atrás de lavadora/secadora | ~5–10 cm (mangueiras e tomada) |
| Ventilação nas laterais | ~2–5 cm |
| Frente de lava e seca / secadora de porta frontal | largura da porta aberta + espaço para a pessoa (~60 cm) |
| Lavadora de tampa superior | tampa aberta: somar ~40–50 cm acima da altura do aparelho |
| Passagem confortável | 60–80 cm |

---

## Privacidade

O repositório `Danielolv14/Modelagem3D-AreaDeCasa` é **público**. Por isso:
- **As fotos da casa não vão para o repositório.** Uso só como referência.
- O modelo 3D só mostra caixas e medidas, nada que identifique o endereço.
- Se preferir tudo privado: tornar o repo privado e publicar pela Vercel. O GitHub
  Pages com repo privado exige plano pago.

---

## Andamento

- [x] Plano e escolha da tecnologia
- [x] Fotos recebidas e lidas: ver [[levantamento-fotos]] (`docs/levantamento-fotos.md`)
- [x] Croqui feito pelo Claude a partir das fotos
- [x] Projeto do Gemini recebido e resumido em [[projeto-reforma]] (`docs/projeto-reforma.md`)
- [x] Simulação 3D, versão 1 (`index.html`), com os cenários "Hoje" e "Com a reforma"
- [x] Painel "E se…?" para ajustar medidas na página
- [x] Plano B: lava-louças de bancada de 8 serviços
- [x] Link público: https://area-de-servico-3d.vercel.app
- [x] Aba "Aparelhos escolhidos": Samsung WD11M4473PX + Midea Touch Plus MDWTF08S com as fotos reais
- [ ] Confirmar onde fica a passagem da cozinha e a largura dela (hoje estimada em 80 cm)
- [ ] Confirmar no manual da Midea a profundidade com a porta aberta (hoje medida pela foto)
- [ ] Decidir onde vão o forno, a sapateira e a lixeira
