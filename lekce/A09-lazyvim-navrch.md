# A09 — LazyVim navrch

Cíl: využít [LazyVim](https://www.lazyvim.org/) — předpřipravenou konfiguraci neovim, která
z něj dělá plnohodnotné IDE (LSP, fuzzy hledání, file tree, git). Tvoje editační gramatika
z předchozích lekcí zůstává; LazyVim jen přidává vrstvu nad ní.

## Leader a which-key — nemusíš si nic pamatovat

Klávesa **`Space`** je „leader". Zmáčkni ji a chvíli počkej — vyskočí **which-key**
nabídka, která ti ukáže, co můžeš stisknout dál. Takže LazyVim se dá „proklikat" bez učení
zkratek nazpaměť. Tohle je nejdůležitější věc celé lekce: **když nevíš, zmáčkni `Space`.**

## Nejčastější akce

| Klávesa | Co |
|---------|-----|
| `Space Space` | najdi soubor (fuzzy, Telescope) |
| `Space /` | hledej text napříč projektem (grep) |
| `Space e` | file explorer (strom) |
| `Space bd` | zavři buffer |
| `Space gg` | otevři lazygit (git UI) |

## LSP — chytré funkce jazyka

Když máš pro jazyk nainstalovaný LSP (LazyVim to nabídne), funguje:

| Klávesa | Co |
|---------|-----|
| `gd` | skoč na definici |
| `gr` | najdi reference |
| `K` | dokumentace pod kurzorem |
| `Space ca` | code action (rychlé opravy) |
| `Space cr` | přejmenuj symbol (rename napříč projektem) |
| `]d` / `[d` | další / předchozí chyba (diagnostika) |

## Komentování a další pohodlí

| Klávesa | Co |
|---------|-----|
| `gcc` | zakomentuj / odkomentuj řádek |
| `gc` (ve Visualu) | zakomentuj výběr |
| `Space cf` | naformátuj soubor |

## Jak zapnout markdown rendering (a další jazyky)

LazyVim má „Extras" — hotové balíčky. Spusť `:LazyExtras`, najeď na položku (např.
`lang.markdown`) a zapni `x`. Tím získáš i pěkné vykreslování Markdownu včetně tabulek.

> Pozn.: ikony a rendering potřebují **Nerd Font** v terminálu, jinak uvidíš čtverečky.

## Cvičení
- [ ] Zmáčkni `Space` a chvíli počkej — projdi which-key nabídku.
- [ ] Otevři soubor přes `Space Space`, prohledej projekt přes `Space /`.
- [ ] Nad nějakou funkcí zkus `K` (docs) a `gd` (definice), zpět přes `Ctrl-o`.

## Co dál
[Lekce A10 — IDE → vim mapa](A10-ide-vim-mapa.md): referenční tahák „co znám z IDE".
