# Direção de arte das ilustrações de projetos

## Sistema visual

- Use pranchas de `1200 × 300 px`, com cantos arredondados e uma borda que contraste com o painel. O formato horizontal deve continuar legível quando reduzido no README.
- Todas as ilustrações usam o fundo ameixa em gradiente (`#171020` → `#38203D`), lavanda (`#C6A0FF`), coral (`#FFAD91`) e branco suave (`#F5EFFF`) para manter a unidade visual com o banner do perfil.
- Use ciano elétrico (`#00E5FF`), magenta (`#FF1E98`) e amarelo (`#FFE500`) como acentos pontuais que retomam a estética cyberpunk do banner. Reserve o verde-água (`#82E0D1`) para sinais de sucesso ou validação, como os indicadores de implantação do ReleaseHub. Preserve a paleta principal nas áreas maiores para que os projetos continuem coesos entre si.
- Prefira formas geométricas simples, contornos arredondados e um foco principal por ilustração. Mantenha uma hierarquia de três pesos no canvas de `1200 × 300 px`:
  - `1,5–2 px` para linhas ambientais e textura, com opacidade baixa (`0,12–0,23`).
  - `3–5 px` para conexões, bordas internas e pistas estruturais.
  - `6–15 px` para silhuetas e gestos do ícone focal, como o atleta, os ponteiros e os sinais de aprovação.
- Use pontas e junções arredondadas nos traços que descrevem o motivo principal. Ícones conceituais podem sugerir o produto, mas não devem parecer capturas reais da interface.
- Confira as ilustrações na largura real do README e em cerca de `320 px`; os elementos focais precisam continuar distinguíveis nessa escala.

## Contraste e acessibilidade

- O painel escuro permanece igual nos temas claro e escuro do GitHub; a borda separa a arte nos fundos claros e continua visível nos escuros. Mantenha os elementos principais em cores claras e saturadas. Opacidades baixas ficam reservadas a linhas e pontos decorativos. Ao revisar, confira os dois extremos do gradiente e a borda contra os fundos claro e escuro da página.
- Preserve contraste forte entre os elementos focais e o fundo. Reavalie os valores se as cores mudarem.
- Não use só a cor para diferenciar significado. Dê a cada projeto uma metáfora visual própria e mantenha uma descrição alternativa no README.
- Cada SVG deve ter `<title>` e `<desc>` concisos, além de dimensões intrínsecas. Escreva o `alt` do README como descrição do conceito mostrado.
