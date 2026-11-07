# Design system playbook

This is a chat-centric web application built around conversations with AI models, with supporting surfaces for authentication (@app/components/auth::AuthPage), session lists, reusable prompt presets called masks, plugins and an MCP market, an image-generation panel under sd/, realtime voice chat, text-to-speech configuration, message export, and settings. The UI is composed from a small in-house primitive layer in ui-lib (modals, lists, inputs, toasts, popovers) plus feature components. Tokens are defined in two main places: app/styles/globals.scss supplies the app-level palette (t19, t59, t60, t62, t36, t40, t41, t21, t35, t61), layout dimensions (t24, t25, t26, t28, t29, t30, t31) and shadows (t32, t33); app/styles/markdown.scss supplies the rendered-markdown palette, including foreground/canvas/border colors (t6–t9, t22, t23, t37, t38), accent/danger/attention colors (t16, t17, t20, t34) and a large set of prettylights syntax-highlighting colors (t0–t5, t10–t15, t18, t42–t58). Two component-scoped tokens exist: t27 in ui-lib.module.scss and t39 in chat.module.scss.

## In one screen

- **Theme lives in:** plain CSS custom properties.
- **Tokens:** 63 in 8 group(s), folded from 123 declaration(s).
- **Themes:** light and dark.
- **Spent:** 61 token(s) are used somewhere; 2 are declared and never used.
- **Components:** 86 declared, 0 primitives, 1 with variants (2 variant value(s)).
- **Disagreements:** 99 instance(s) in 3 kind(s). See the last section.

## Where the design is declared

| file | what it declares |
| --- | --- |
| `app/components/home.module.scss`:25 | 3 custom properties declared under `.tight-container`. |
| `app/components/ui-lib.module.scss`:92 | 1 custom property declared under `.modal-container`. |
| `app/components/ui-lib.module.scss`:172 | 1 custom property declared under `.modal-container`. |
| `app/styles/globals.scss`:59 | 11 custom properties declared under `:root`. |
| `app/styles/globals.scss`:71 | 11 custom properties declared under `:root`. |
| `app/styles/globals.scss`:85 | 11 custom properties declared under `:root`. |
| `app/styles/globals.scss`:120 | 1 custom property declared under `::-webkit-scrollbar`. |

## Palette

Colour is written in hex (40 token(s)), rgb (6 token(s)), rgba (2 token(s)), hsla (1 token(s)). 0 colour token(s) have zero chroma (pure greys) and 1 carry a hue: `--color-border-muted`. 51 colour token(s) are re-declared for dark mode; 0 keep their light value.

### Surfaces (8)

#### bg

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-prettylights-syntax-carriage-return-bg` |  | `#cf222e` | `#b62324` | 1 | `app/styles/markdown.scss`:15 |
| `--color-prettylights-syntax-invalid-illegal-bg` |  | `#82071e` | `#8e1519` | 1 | `app/styles/markdown.scss`:13 |
| `--color-prettylights-syntax-markup-changed-bg` |  | `#ffd8b5` | `#5a1e02` | 1 | `app/styles/markdown.scss`:26 |
| `--color-prettylights-syntax-markup-deleted-bg` |  | `#ffebe9` | `#67060c` | 1 | `app/styles/markdown.scss`:22 |
| `--color-prettylights-syntax-markup-ignored-bg` |  | `#0550ae` | `#1158c7` | 1 | `app/styles/markdown.scss`:28 |
| `--color-prettylights-syntax-markup-inserted-bg` |  | `#dafbe1` | `#033a16` | 1 | `app/styles/markdown.scss`:24 |

#### muted

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-fg-muted` |  | `#57606a` | `#8b949e` | 3 | `app/styles/markdown.scss`:34 |
| `--color-neutral-muted` |  | `rgba(175, 184, 193, 0.2)` | `rgba(110, 118, 129, 0.4)` | 4 | `app/styles/markdown.scss`:40 |

### Text (8)

#### fg

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-fg-default` |  | `#24292f` | `#c9d1d9` | 6 | `app/styles/markdown.scss`:33 |
| `--color-fg-subtle` |  | `#6e7781` | `#6e7681` | 1 | `app/styles/markdown.scss`:35 |

#### text

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-prettylights-syntax-carriage-return-text` |  | `#f6f8fa` | `#f0f6fc` | 1 | `app/styles/markdown.scss`:14 |
| `--color-prettylights-syntax-invalid-illegal-text` |  | `#f6f8fa` | `#f0f6fc` | 1 | `app/styles/markdown.scss`:12 |
| `--color-prettylights-syntax-markup-changed-text` |  | `#953800` | `#ffdfb6` | 1 | `app/styles/markdown.scss`:25 |
| `--color-prettylights-syntax-markup-deleted-text` |  | `#82071e` | `#ffdcd7` | 1 | `app/styles/markdown.scss`:21 |
| `--color-prettylights-syntax-markup-ignored-text` |  | `#eaeef2` | `#c9d1d9` | 1 | `app/styles/markdown.scss`:27 |
| `--color-prettylights-syntax-markup-inserted-text` |  | `#116329` | `#aff5b4` | 1 | `app/styles/markdown.scss`:23 |

### Brand (4)

#### accent

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-accent-emphasis` |  | `#0969da` | `#1f6feb` | 1 | `app/styles/markdown.scss`:42 |
| `--color-accent-fg` |  | `#0969da` | `#58a6ff` | 3 | `app/styles/markdown.scss`:41 |

#### link

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-prettylights-syntax-constant-other-reference-link` |  | `#0a3069` | `#a5d6ff` | 1 | `app/styles/markdown.scss`:32 |

#### primary

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--primary` |  | `rgb(29, 147, 171)` | (same) | 34 | `app/styles/globals.scss`:11 |

### Status (1)

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-danger-fg` |  | `#cf222e` | `#f85149` | 1 | `app/styles/markdown.scss`:44 |

### Controls (border, input, ring) (3)

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--border-in-light` |  | `1px solid rgb(222, 222, 222)` | `1px solid rgba(255, 255, 255, 0.192)` | 51 | `app/styles/globals.scss`:22 |
| `--color-border-default` |  | `#d0d7de` | `#30363d` | 5 | `app/styles/markdown.scss`:38 |
| `--color-border-muted` |  | `hsla(210, 18%, 87%, 1)` | `#21262d` | 4 | `app/styles/markdown.scss`:39 |

### Elevation (2)

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--card-shadow` |  | `0px 2px 4px 0px rgb(0, 0, 0, 0.05)` | _none_ | 21 | `app/styles/globals.scss`:19 |
| `--shadow` |  | `50px 50px 100px 10px rgb(0, 0, 0, 0.1)` | _none_ | 3 | `app/styles/globals.scss`:18 |

### Unclassified (29)

| token | utility name | light | dark | uses | defined at |
| --- | --- | --- | --- | --- | --- |
| `--color-attention-subtle` |  | `#fff8c5` | `rgba(187, 128, 9, 0.15)` | 1 | `app/styles/markdown.scss`:43 |
| `--bar-color` |  | `rgba(0, 0, 0, 0.1)` | `rgba(255, 255, 255, 0.1)` | 1 | `app/styles/globals.scss`:14 |
| `--black` |  | `rgb(48, 48, 48)` | `rgb(187, 187, 187)` | 35 | `app/styles/globals.scss`:9 |
| `--color-canvas-default` |  | `transparent` | (same) | 4 | `app/styles/markdown.scss`:36 |
| `--color-canvas-subtle` |  | `#f6f8fa` | `#161b22` | 3 | `app/styles/markdown.scss`:37 |
| `--delay` |  | `0.5s` | (same) | 2 | `app/components/chat.module.scss`:83 |
| `--gray` |  | `rgb(250, 250, 250)` | `rgb(21, 21, 21)` | 10 | `app/styles/globals.scss`:10 |
| `--hover-color` |  | `#f3f3f3` | `#323232` | 1 | `app/styles/globals.scss`:13 |
| `--color-prettylights-syntax-brackethighlighter-angle` |  | `#57606a` | `#8b949e` | 1 | `app/styles/markdown.scss`:30 |
| `--color-prettylights-syntax-brackethighlighter-unmatched` |  | `#82071e` | `#f85149` | 1 | `app/styles/markdown.scss`:11 |
| `--color-prettylights-syntax-comment` |  | `#6e7781` | `#8b949e` | 1 | `app/styles/markdown.scss`:3 |
| `--color-prettylights-syntax-constant` |  | `#0550ae` | `#79c0ff` | 1 | `app/styles/markdown.scss`:4 |
| `--color-prettylights-syntax-entity` |  | `#8250df` | `#d2a8ff` | 1 | `app/styles/markdown.scss`:5 |
| `--color-prettylights-syntax-entity-tag` |  | `#116329` | `#7ee787` | 1 | `app/styles/markdown.scss`:7 |
| `--color-prettylights-syntax-keyword` |  | `#cf222e` | `#ff7b72` | 1 | `app/styles/markdown.scss`:8 |
| `--color-prettylights-syntax-markup-bold` |  | `#24292f` | `#c9d1d9` | 1 | `app/styles/markdown.scss`:20 |
| `--color-prettylights-syntax-markup-heading` |  | `#0550ae` | `#1f6feb` | 1 | `app/styles/markdown.scss`:18 |
| `--color-prettylights-syntax-markup-italic` |  | `#24292f` | `#c9d1d9` | 1 | `app/styles/markdown.scss`:19 |
| `--color-prettylights-syntax-markup-list` |  | `#3b2300` | `#f2cc60` | 1 | `app/styles/markdown.scss`:17 |
| `--color-prettylights-syntax-meta-diff-range` |  | `#8250df` | `#d2a8ff` | 1 | `app/styles/markdown.scss`:29 |
| `--color-prettylights-syntax-storage-modifier-import` |  | `#24292f` | `#c9d1d9` | 1 | `app/styles/markdown.scss`:6 |
| `--color-prettylights-syntax-string` |  | `#0a3069` | `#a5d6ff` | 1 | `app/styles/markdown.scss`:9 |
| `--color-prettylights-syntax-string-regexp` |  | `#116329` | `#7ee787` | 1 | `app/styles/markdown.scss`:16 |
| `--color-prettylights-syntax-sublimelinter-gutter-mark` |  | `#8c959f` | `#484f58` | 1 | `app/styles/markdown.scss`:31 |
| `--color-prettylights-syntax-variable` |  | `#953800` | `#ffa657` | 1 | `app/styles/markdown.scss`:10 |
| `--second` |  | `rgb(231, 248, 255)` | `rgb(27 38 42)` | 11 | `app/styles/globals.scss`:12 |
| `--theme` |  | `light` | `dark` | 0 | `app/styles/globals.scss`:5 |
| `--theme-color` |  | `rgb(250, 250, 250)` | `rgb(21, 21, 21)` | 0 | `app/styles/globals.scss`:15 |
| `--white` |  | `white` | `rgb(30, 30, 30)` | 43 | `app/styles/globals.scss`:8 |

## Scales

### Spacing

| step | expression | computed | uses | defined at |
| --- | --- | --- | --- | --- |
| `--bar-width` | `10px` | 10px | 2 | `app/styles/globals.scss`:121 |
| `--modal-padding` | `20px` | 20px | 3 | `app/components/ui-lib.module.scss`:101 |
| `--full-height` | `100%` |  | 7 | `app/styles/globals.scss`:67 |
| `--message-max-width` | `100%` |  | 1 | `app/styles/globals.scss`:76 |
| `--sidebar-width` | `100vw` |  | 6 | `app/styles/globals.scss`:74 |
| `--window-content-width` | `var(--window-width)` |  | 1 | `app/styles/globals.scss`:75 |
| `--window-height` | `var(--full-height)` |  | 1 | `app/styles/globals.scss`:73 |
| `--window-width` | `100vw` |  | 3 | `app/styles/globals.scss`:72 |

### Typography

| family | declared at |
| --- | --- |
| `inherit` | `app/components/chat.module.scss`:650 |
| `"Noto Sans", "SF Pro SC", "SF Pro Text", "SF Pro Icons",
    "PingFang SC", "Helvetica Neue", "Helvetica", "Arial", sans-serif` | `app/styles/globals.scss`:93 |
| `Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace` | `app/styles/highlight.scss`:8 |
| `monospace` | `app/styles/markdown.scss`:221 |
| `ui-monospace, SFMono-Regular, SF Mono, Menlo, Consolas,
    Liberation Mono, monospace` | `app/styles/markdown.scss`:451 |
| `"Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol"` | `app/styles/markdown.scss`:1061 |

| step | size | weight | declared at |
| --- | --- | --- | --- |
| `Heading 1` | `2em` |  | `app/styles/markdown.scss`:175 |
| `Heading 2` | `1.5em` |  | `app/styles/markdown.scss`:383 |
| `Heading 3` | `1.25em` |  | `app/styles/markdown.scss`:390 |
| `Heading 4` | `1em` |  | `app/styles/markdown.scss`:395 |
| `Heading 5` | `0.875em` |  | `app/styles/markdown.scss`:400 |
| `Heading 6` | `0.85em` |  | `app/styles/markdown.scss`:405 |

## States the UI actually targets

| state | class occurrences |
| --- | --- |
| `focus` | 1 |

## Composition

No primitives directory was found, so every component is an application component: there is an inventory here but no shared kit to build from.

## Where the app disagrees with itself

### 33 colour tokens share only 13 distinct value(s) in light mode

51 colour token(s) resolve to 31 distinct light value(s). Where two names always carry the same value, a reader cannot tell which one a screen should use:
- #cf222e: --color-prettylights-syntax-carriage-return-bg, --color-danger-fg, --color-prettylights-syntax-keyword
- #82071e: --color-prettylights-syntax-invalid-illegal-bg, --color-prettylights-syntax-markup-deleted-text, --color-prettylights-syntax-brackethighlighter-unmatched
- #0550ae: --color-prettylights-syntax-markup-ignored-bg, --color-prettylights-syntax-constant, --color-prettylights-syntax-markup-heading
- #57606a: --color-fg-muted, --color-prettylights-syntax-brackethighlighter-angle
- #24292f: --color-fg-default, --color-prettylights-syntax-markup-bold, --color-prettylights-syntax-markup-italic, --color-prettylights-syntax-storage-modifier-import
- #6e7781: --color-fg-subtle, --color-prettylights-syntax-comment
- #f6f8fa: --color-prettylights-syntax-carriage-return-text, --color-prettylights-syntax-invalid-illegal-text, --color-canvas-subtle
- #953800: --color-prettylights-syntax-markup-changed-text, --color-prettylights-syntax-variable
- #116329: --color-prettylights-syntax-markup-inserted-text, --color-prettylights-syntax-entity-tag, --color-prettylights-syntax-string-regexp
- #0969da: --color-accent-emphasis, --color-accent-fg
- #0a3069: --color-prettylights-syntax-constant-other-reference-link, --color-prettylights-syntax-string
- rgb(250, 250, 250): --gray, --theme-color
- #8250df: --color-prettylights-syntax-entity, --color-prettylights-syntax-meta-diff-range

- `app/styles/markdown.scss`:15: `--color-prettylights-syntax-carriage-return-bg: #cf222e`
- `app/styles/markdown.scss`:44: `--color-danger-fg: #cf222e`
- `app/styles/markdown.scss`:8: `--color-prettylights-syntax-keyword: #cf222e`
- `app/styles/markdown.scss`:13: `--color-prettylights-syntax-invalid-illegal-bg: #82071e`
- `app/styles/markdown.scss`:21: `--color-prettylights-syntax-markup-deleted-text: #82071e`
- `app/styles/markdown.scss`:11: `--color-prettylights-syntax-brackethighlighter-unmatched: #82071e`

### 2 token(s) are declared and never used

No utility class and no `var()` reference spends them: --theme-color, --theme.

- `app/styles/globals.scss`:15: `--theme-color: var(--gray)`
- `app/styles/globals.scss`:5: `--theme: light`

### 64 hardcoded colour literal(s) bypass the tokens

Written into a colour property or an arbitrary class value; 21 duplicate a token that already exists.

- `app/components/button.module.scss`:31: `color: rgba($color: red, $alpha: 0.8);`
- `app/components/button.module.scss`:32: `border-color: rgba($color: red, $alpha: 0.5);`
- `app/components/button.module.scss`:33: `background-color: rgba($color: red, $alpha: 0.05);`
- `app/components/button.module.scss`:37: `background-color: rgba($color: red, $alpha: 0.1);`
- `app/components/chat.module.scss`:14: `border: rgba($color: #888, $alpha: 0.2) 1px solid;`
- `app/components/chat.module.scss`:14: `border: rgba($color: #888, $alpha: 0.2) 1px solid;`
- `app/components/chat.module.scss`:153: `background-color: rgba(0, 0, 0, 0);`
- `app/components/chat.module.scss`:161: `background-color: rgba(0, 0, 0, 0.05);`
- `app/components/chat.module.scss`:417: `color: #aaa;`
- `app/components/chat.module.scss`:424: `color: #aaa;`

### Every hardcoded colour, by file

| file | literal | duplicates |
| --- | --- | --- |
| `app/components/button.module.scss`:31 | `rgba($color: red, $alpha: 0.8)` |  |
| `app/components/button.module.scss`:32 | `rgba($color: red, $alpha: 0.5)` |  |
| `app/components/button.module.scss`:33 | `rgba($color: red, $alpha: 0.05)` |  |
| `app/components/button.module.scss`:37 | `rgba($color: red, $alpha: 0.1)` |  |
| `app/components/chat.module.scss`:14 | `#888` |  |
| `app/components/chat.module.scss`:14 | `rgba($color: #888, $alpha: 0.2)` |  |
| `app/components/chat.module.scss`:153 | `rgba(0, 0, 0, 0)` | `--bar-color` |
| `app/components/chat.module.scss`:161 | `rgba(0, 0, 0, 0.05)` | `--bar-color` |
| `app/components/chat.module.scss`:417 | `#aaa` |  |
| `app/components/chat.module.scss`:424 | `#aaa` |  |
| `app/components/chat.module.scss`:442 | `rgba(0, 0, 0, 0.05)` | `--bar-color` |
| `app/components/chat.module.scss`:457 | `rgba(0, 0, 0, 0.05)` | `--bar-color` |
| `app/components/chat.module.scss`:496 | `#888` |  |
| `app/components/chat.module.scss`:496 | `rgba($color: #888, $alpha: 0.2)` |  |
| `app/components/chat.module.scss`:647 | `rgba(0, 0, 0, 0.03)` | `--bar-color` |
| `app/components/exporter.module.scss`:245 | `#888` |  |
| `app/components/exporter.module.scss`:245 | `rgba($color: #888, $alpha: 0.2)` |  |
| `app/components/home.module.scss`:48 | `rgb(0, 0, 0, 0.05)` | `--bar-color` |
| `app/components/home.module.scss`:68 | `#000000` | `--bar-color` |
| `app/components/home.module.scss`:68 | `rgba($color: #000000, $alpha: 0.01)` |  |
| `app/components/home.module.scss`:85 | `#000000` | `--bar-color` |
| `app/components/home.module.scss`:85 | `rgba($color: #000000, $alpha: 0)` |  |
| `app/components/home.module.scss`:229 | `rgb(166, 166, 166)` |  |
| `app/components/mcp-market.module.scss`:115 | `#16a34a` |  |
| `app/components/mcp-market.module.scss`:116 | `#fff` | `--border-in-light` |
| `app/components/mcp-market.module.scss`:120 | `#9ca3af` |  |
| `app/components/mcp-market.module.scss`:124 | `#4ade80` |  |
| `app/components/mcp-market.module.scss`:128 | `#f87171` |  |
| `app/components/mcp-market.module.scss`:159 | `#22c55e` |  |
| `app/components/mcp-market.module.scss`:160 | `#fff` | `--border-in-light` |
| `app/components/mcp-market.module.scss`:163 | `#ef4444` |  |
| `app/components/mcp-market.module.scss`:167 | `#6b7280` |  |
| `app/components/mcp-market.module.scss`:171 | `#f59e0b` |  |
| `app/components/realtime-chat/realtime-chat.module.scss`:15 | `#a0d8ef` |  |
| `app/components/realtime-chat/realtime-chat.module.scss`:15 | `#f0f8ff` |  |
| `app/components/tts.module.scss`:86 | `#f86c6c` |  |
| `app/components/ui-lib.module.scss`:33 | `rgba(0, 0, 0, 0.3)` | `--bar-color` |
| `app/components/ui-lib.module.scss`:287 | `rgba(0, 0, 0, 0.03)` | `--bar-color` |
| `app/components/ui-lib.module.scss`:307 | `rgba(0, 0, 0, 0.5)` | `--bar-color` |
| `app/styles/globals.scss`:253 | `#000000` | `--bar-color` |
| `app/styles/globals.scss`:253 | `rgba($color: #000000, $alpha: 0.5)` |  |
| `app/styles/globals.scss`:328 | `#464e4e` |  |
| `app/styles/globals.scss`:336 | `rgba(0, 0, 0, 0.8)` | `--bar-color` |
| `app/styles/globals.scss`:336 | `rgba(0, 0, 0, 0.06)` | `--bar-color` |
| `app/styles/highlight.scss`:23 | `#1a1b26` |  |
| `app/styles/highlight.scss`:24 | `#cbd2ea` |  |
| `app/styles/highlight.scss`:37 | `#565f89` |  |
| `app/styles/highlight.scss`:50 | `#f7768e` |  |
| `app/styles/highlight.scss`:60 | `#ff9e64` |  |
| `app/styles/highlight.scss`:65 | `#e0af68` |  |
| `app/styles/highlight.scss`:75 | `#7dcfff` |  |
| `app/styles/highlight.scss`:79 | `#73daca` |  |
| `app/styles/highlight.scss`:87 | `#9ece6a` |  |
| `app/styles/highlight.scss`:93 | `#7aa2f7` |  |
| `app/styles/highlight.scss`:101 | `#bb9af7` |  |
| `app/styles/highlight.scss`:105 | `#c0caf5` |  |
| `app/styles/window.scss`:3 | `rgba(0, 0, 0, 0.1)` | `--bar-color` |
| `app/components/home.tsx`:107 | `#151515` | `--gray` |
| `app/components/home.tsx`:108 | `#fafafa` | `--gray` |
| `app/components/voice-print/voice-print.tsx`:155 | `rgba(100, 180, 255, 0.95)` |  |
| `app/components/voice-print/voice-print.tsx`:156 | `rgba(140, 200, 255, 0.9)` |  |
| `app/components/voice-print/voice-print.tsx`:157 | `rgba(180, 220, 255, 0.95)` |  |
| `app/layout.tsx`:25 | `#fafafa` | `--gray` |
| `app/layout.tsx`:26 | `#151515` | `--gray` |
