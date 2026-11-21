# eskgo-tokens

Design tokens do **Eskgo**, o app de finanças pessoais. Dois temas com os mesmos nomes de token (`--esk-*`):

- **Escuro**: a identidade do Eskgo, com fundo quase preto, lima `#E5FFB5` e lilás `#D8CCFA`.
- **Claro**: os valores do design system **Calmo**, com fundo stone quente `#F6F6F1`, indigo e lima, e texto que passa no WCAG AA.

## Arquivos

| Arquivo | Formato | Uso |
|---|---|---|
| `tokens/base.tokens.json` | W3C DTCG | Tokens comuns aos dois temas: raios, espaçamento (grade de 4 pt), breakpoints, fontes e escala de tipografia |
| `tokens/dark.tokens.json` | W3C DTCG | Tema escuro |
| `tokens/light.tokens.json` | W3C DTCG | Tema claro |
| `css/eskgo.css` | CSS custom properties | Escuro em `:root`; claro em `:root[data-theme="light"]` |
| `tailwind/eskgo.css` | Tailwind CSS v4 `@theme` | Utilitários `bg-surface`, `text-fg-muted`, `bg-lime`, `text-lime-ink`, `rounded-card`, `md:` (800px) e `lg:` (1100px) |

## Como usar

**Tailwind v4 (app Next.js do Eskgo):**

```css
@import "tailwindcss";
@import "eskgo-tokens/tailwind/eskgo.css";
```

**CSS puro:**

```css
@import "eskgo-tokens/css/eskgo.css";
```

Para ativar o tema claro, coloque `<html data-theme="light">`.

**Figma, com o plugin Tokens Studio:** importe `tokens/base.tokens.json` junto com `dark.tokens.json` ou `light.tokens.json`. Cada tema vira um conjunto de tokens, e os conjuntos viram Variables com um modo para o escuro e outro para o claro.

**Instalar a partir do GitHub:**

```bash
npm install github:Lica-git/eskgo-tokens
```

## Regras de uso

- **Lima e lilás são fundos.** O texto sobre eles usa `on-brand`. Quando o lima precisa aparecer como texto (links, "Ver todas", variações positivas), use `role.lime-ink`: ele é o próprio lima no tema escuro e `#46741A` no claro.
- **Barras e anéis de progresso** usam `role.progress`. As cores de categoria têm duas versões: `fill`, para blocos, e `bar`, para traços finos (mais forte no tema claro).
- **Gasto não é vermelho.** Um valor negativo leva o sinal "−". `brand.danger` é só para erro ou para quando a pessoa passou do teto.
- **Foco do teclado:** contorno de 2px em `role.focus`.
