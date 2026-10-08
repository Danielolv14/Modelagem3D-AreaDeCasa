# Modelagem 3D — Área de Serviço

Simulação 3D interativa (Three.js) da área de serviço de casa, para visualizar se
os novos equipamentos cabem no espaço.

## Como abrir
- Link público: **https://area-de-servico-3d.vercel.app**
- Ou abrir o `index.html` no navegador (precisa de internet para carregar o Three.js).

## Como corrigir uma medida
- **Pela página:** o painel "E se…?" muda corredor, fundo da bancada, largura da passagem e a
  profundidade com a porta aberta dos aparelhos. Fica guardado só naquele navegador.
- **No código:** as medidas ficam em `PADRAO` e `montarMedidas()`, no começo do script do
  `index.html`, em centímetros. Os valores marcados com `(E)` foram estimados pelas fotos.

## Notas
- Plano e tecnologia: [PLANO.md](PLANO.md)
- Projeto da reforma e medidas dos aparelhos: [docs/projeto-reforma.md](docs/projeto-reforma.md)
- O que foi identificado nas fotos: [docs/levantamento-fotos.md](docs/levantamento-fotos.md)
- Prompt para extrair medidas do Gemini: [docs/prompt-gemini.md](docs/prompt-gemini.md)
