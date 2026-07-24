# Recept — Markdown v neovim: rendering, tabulky, náhled

Neovim umí Markdown vykreslovat **přímo v editoru** — nadpisy, checkboxy, rámečky kolem
kódu a hlavně pěkně zarovnané tabulky — a přitom pořád edituješ prostý text.

## Zapnutí

`:LazyExtras` → najeď na **`lang.markdown`** → `x`. Tím dostaneš:

| Co | K čemu |
|----|--------|
| **render-markdown.nvim** | inline rendering: nadpisy, checkboxy, callouty, **tabulky** |
| **marksman** (LSP) | doplňování a kontrola odkazů, symboly dokumentu |
| **markdown-preview** | `:MarkdownPreview` — živý náhled v prohlížeči |

Podmínka: **Nerd Font** v terminálu, jinak místo ikon uvidíš čtverečky.

## Práce s dokumentem

- Řádek pod kurzorem se „rozbalí" do zdrojové podoby — rendering editaci nepřekáží.
- Přepínač renderingu: `:RenderMarkdown toggle`.
- **Osnova dokumentu:** `Space ss` — nadpisy jako symboly, skáčeš po sekcích.
- Odkazy mezi soubory našeptává marksman (začni psát `[](` a nabídne cíle).

## Tabulky

render-markdown zarovná **vzhled** tabulky box-drawing rámečky i u rozházeného zdroje.
Když chceš rovnat i **zdroják** při psaní (dopíšeš buňku a sloupce se srovnají), přidej
si plugin **vim-table-mode** — s renderingem se pěkně doplňuje.

## Obrázky

V terminálech kitty/ghostty umí LazyVim zobrazit obrázky přímo v bufferu (snacks image).
**V tmuxu je to ošemetné** (grafický protokol se přes něj špatně protlačuje) — tam počítej
spíš s náhledem v prohlížeči přes `:MarkdownPreview`.

## Cvičení
- [ ] Zapni Extra `lang.markdown` a otevři [cheatsheet](../cheatsheet.md) tohohle repa —
      tabulky by měly dostat rámečky.
- [ ] `Space ss` → skoč na sekci „Text objekty".
- [ ] Přepni `:RenderMarkdown toggle` tam a zpět.
- [ ] Spusť `:MarkdownPreview` a sleduj živý náhled při psaní.
