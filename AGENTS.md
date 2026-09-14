# AGENTS.md — ai.andersond (landing page)

Site estático da marca pessoal **@ai.andersond**: `index.html` + `tokens.css` + `styles.css`. Sem build, sem framework, sem JavaScript. Leia isto antes de editar qualquer arquivo.

## Fonte de verdade

- `tokens.json` (W3C Design Tokens, v1.0.0) é **normativo**. `tokens.css` só o espelha: mudou um, mude o outro na mesma passada.
- Produção: https://ai-andersond.vercel.app (Vercel). As URLs absolutas de `og:url`, `og:image`, `twitter:image` e `canonical` em `index.html` apontam para lá; se o domínio mudar, trocar as quatro.
- O documento de identidade ("Identidade Visual — Direção Lousa") vive no vault do Anderson em `Anderson - SM/01 - Identidade Visual/`; os originais estão em `/Users/mac/Downloads/identidade-visual-anderson/`. Este repo **implementa** a identidade, não a redefine.

## Regras que não se negociam

1. **Cores:** só os 6 hex dos tokens. Copiar, nunca aproximar.
2. **Cobre `#D2823F` só no ponto da marca** (`.dot`, `favicon.svg`, `apple-touch-icon.png`, `assets/og.html`). Se aparecer em outro lugar, está errado.
3. **Menta `#9ED3BC` é acento:** linha de 2px, numeral, uma expressão dentro de uma frase. Nunca um título inteiro, nunca fundo de botão.
4. **Não existem:** gradiente, sombra, caixa alta, emoji, seta, ícone de robô, animação decorativa.
5. **Raio 0** em tudo, exceto `.dot` (2px) e `.photo` (8px).
6. **Uma família:** Bricolage Grotesque. Título 700, tracking -0.02em, entrelinha 1.02. Texto 400. Rótulo 500. Escala: 12 · 14 · 16 · 20 · 26 · 34 · 44 · 58 · 76.
7. **Alinhado à esquerda**, ancorado ao rodapé. Margem lateral = 6% (`.wrap`). Grade de 12 colunas (`.grid`).
8. **Proporção por tela:** ~80% lousa, ~15% giz, ~5% menta.

## Regras de texto

- Público: **profissional não técnico** no Brasil (corretor, advogado, professor, contador, vendedor, dono de comércio, administrativo, saúde autônomo, RH, social media freela). Não escreva para dev ou tech lead.
- Zero termo técnico sem tradução na mesma frase.
- Título em caixa de frase, sem exclamação, **até 6 palavras** no hero e nas capas.
- Uma profissão **ou** um princípio por peça. Nunca os dois.
- Números com denominador ("3 de 7"), nunca soltos.
- **Não inventar** fato, link ou handle. Confirmados hoje: Instagram `@ai.andersond` e `aureatech.io`. Tudo o mais é pendência (ver README).

## Onde mexer

| Quero mudar… | Onde |
|---|---|
| Texto do hero | `index.html` › `section.hero` |
| Profissões e tarefas | `index.html` › `ul.who` |
| Capas de temas | `index.html` › `ul.covers` |
| Bio e princípios | `index.html` › `section.about` |
| Cor, tipo, espaço, raio | `tokens.json` **e** `tokens.css` |
| Layout e responsivo | `styles.css` |
| Imagem de compartilhamento | `assets/og.html`, depois regenerar `assets/og.png` (README) |
| Fotos (Fase 2) | `figure.photo` › trocar placeholder por `<img>`; pasta `assets/fotos/` |

## Antes de commitar

- [ ] Abrir em 1440px e em 390px. Nada rola na horizontal.
- [ ] Contar o cobre em cada tela: só o ponto da marca.
- [ ] `grep -n "gradient\|shadow\|uppercase\|!important" styles.css` retorna só comentários.
- [ ] Todo link externo com `target="_blank" rel="noopener"`.
- [ ] Sem git no vault: este repo é o único lugar versionado da landing.
