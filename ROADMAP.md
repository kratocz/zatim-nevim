# Roadmapa

Kam kurz míří. Značky stavu: ✅ hotovo · 🚧 rozpracováno · 🔜 plánováno.

Kurz je rozdělený do tří **tracků**. Track A je lineární cesta od nuly; tracky B a C jsou
goal-oriented — čteš je, když víš, *co* chceš udělat, a hledáš *jak*.

## Track A — Kurz od nuly ✅

Lineární výuka od „umím jen spustit vim" po plynulé ovládání.

| # | Lekce | Stav |
|---|-------|------|
| 00 | [Nouzové přežití](lekce/00-nouzove-preziti.md) | ✅ |
| 01 | [Přežití](lekce/01-preziti.md) | ✅ |
| 02 | [Tři režimy pořádně](lekce/02-tri-rezimy.md) | ✅ |
| 03 | [Pohyb](lekce/03-pohyb.md) | ✅ |
| 04 | [Editační gramatika](lekce/04-gramatika.md) | ✅ |
| 05 | [Kopírování a registry](lekce/05-kopirovani-registry.md) | ✅ |
| 06 | [Hledání a nahrazování](lekce/06-hledani-a-nahrazovani.md) | ✅ |
| 07 | [Undo, opakování, makra](lekce/07-undo-opakovani-makra.md) | ✅ |
| 08 | [Více souborů](lekce/08-vice-souboru.md) | ✅ |
| 09 | [LazyVim navrch](lekce/09-lazyvim-navrch.md) | ✅ |
| 10 | [IDE → vim mapa](lekce/10-ide-vim-mapa.md) | ✅ |

## Track B — Přechod z IDE 🚧

Pro lidi přicházející z VS Code nebo JetBrains. Goal-oriented: každá lekce odpovídá na
reálný dotaz typu *„jak ve vim udělám to, co v IDE dělám takhle"*. Rozšíření populární
lekce 10 do samostatné kapitoly ([`prechod-z-ide/`](prechod-z-ide/)).

| # | Lekce | O čem | Stav |
|---|-------|-------|------|
| B0 | [vim *uvnitř* tvého IDE](prechod-z-ide/00-vim-uvnitr-ide.md) | VSCodeVim / IdeaVim — uč se gramatiku bez opuštění známého prostředí | ✅ |
| B1 | [Multi-cursor po vimácku](prechod-z-ide/01-multicursor.md) | `Cmd+D` → `cgn`+`.`, visual-block `Ctrl-v`, makra, `:g/…/normal` | ✅ |
| B2 | [`:g` global command](prechod-z-ide/02-global-command.md) | dávková editace — „udělej X na každém řádku, kde je Y" | ✅ |
| B3 | [Z VS Code do vim](prechod-z-ide/03-vscode.md) | mentální posuny, mapa zkratek, strategie přechodu | ✅ |
| B4 | [Z JetBrains do vim](prechod-z-ide/04-jetbrains.md) | mapování akcí (Alt+Enter…), IdeaVim jako mezistanice, hybrid | ✅ |
| B5 | Refaktoring | rename, extract, organize imports → LSP code actions | 🔜 |
| B6 | Git jako GitLens | gitsigns, hunky, blame, `Space gg` (lazygit) | 🔜 |
| B7 | Multi-file & workspace | goto file/symbol, splity, file tree, jump list | 🔜 |
| B8 | Autocomplete & snippety | IntelliSense → nvim-cmp / blink | 🔜 |
| B9 | Debugging | breakpointy, step → nvim-dap | 🔜 |

**Hotovo:** B0–B4. **Nejbližší na řadě:** B5 (Refaktoring), B6 (Git jako GitLens).

## Track C — Recepty 🔜

Task taháky ve stylu lekce 10, ale čistě editační. „Chci udělat X → napiš Y."

| Lekce | O čem | Stav |
|-------|-------|------|
| Surround | `ys` / `cs` / `ds` — obalování do závorek, uvozovek, tagů | 🔜 |
| Ex příkazy & rozsahy | `:m` (move), `:t` (copy), `:normal`, `:%!sort` — vim jako dávkový editor | 🔜 |
| Marks & jumpy | `ma`, `` `a ``, `Ctrl-o/i` — navigace ve velkém souboru | 🔜 |
| Makra do hloubky | praktické recepty, rekurzivní makra | 🔜 |
| 50 nejčastějších úkonů | velký task tahák | 🔜 |
| Markdown v neovim | render-markdown + tabulky, `:LazyExtras lang.markdown` | 🔜 |
| Konfigurace LazyVim | přidat plugin, keymapu, option | 🔜 |
| Nerd Fonts & terminál v nvim | okolní setup, `:terminal` / `Ctrl-/` | 🔜 |

## Jak to roste

Tempo drží autor; lekce přibývají postupně. Track A je páteř, tracky B a C se plní podle
toho, co je nejužitečnější (a nejvyhledávanější). Návrhy vítány přes issues.
