# Roadmapa

Kam kurz míří. Značky stavu: ✅ hotovo · 🚧 rozpracováno · 🔜 plánováno.

Kurz je rozdělený do tří **tracků**. Track A je lineární cesta od nuly; tracky B a C jsou
goal-oriented — čteš je, když víš, *co* chceš udělat, a hledáš *jak*.

## Track A — Kurz od nuly ✅

Lineární výuka od „umím jen spustit vim" po plynulé ovládání.

| # | Lekce | Stav |
|---|-------|------|
| A00 | [Nouzové přežití](lekce/A00-nouzove-preziti.md) | ✅ |
| A01 | [Přežití](lekce/A01-preziti.md) | ✅ |
| A02 | [Tři režimy pořádně](lekce/A02-tri-rezimy.md) | ✅ |
| A03 | [Pohyb](lekce/A03-pohyb.md) | ✅ |
| A04 | [Editační gramatika](lekce/A04-gramatika.md) | ✅ |
| A05 | [Kopírování a registry](lekce/A05-kopirovani-registry.md) | ✅ |
| A06 | [Hledání a nahrazování](lekce/A06-hledani-a-nahrazovani.md) | ✅ |
| A07 | [Undo, opakování, makra](lekce/A07-undo-opakovani-makra.md) | ✅ |
| A08 | [Více souborů](lekce/A08-vice-souboru.md) | ✅ |
| A09 | [LazyVim navrch](lekce/A09-lazyvim-navrch.md) | ✅ |
| A10 | [IDE → vim mapa](lekce/A10-ide-vim-mapa.md) | ✅ |

## Track B — Přechod z IDE ✅

Pro lidi přicházející z VS Code nebo JetBrains. Goal-oriented: každá lekce odpovídá na
reálný dotaz typu *„jak ve vim udělám to, co v IDE dělám takhle"*. Rozšíření populární
lekce A10 do samostatné kapitoly ([`prechod-z-ide/`](prechod-z-ide/)).

| # | Lekce | O čem | Stav |
|---|-------|-------|------|
| B00 | [vim *uvnitř* tvého IDE](prechod-z-ide/B00-vim-uvnitr-ide.md) | VSCodeVim / IdeaVim — uč se gramatiku bez opuštění známého prostředí | ✅ |
| B01 | [Multi-cursor po vimácku](prechod-z-ide/B01-multicursor.md) | `Cmd+D` → `cgn`+`.`, visual-block `Ctrl-v`, makra, `:g/…/normal` | ✅ |
| B02 | [`:g` global command](prechod-z-ide/B02-global-command.md) | dávková editace — „udělej X na každém řádku, kde je Y" | ✅ |
| B03 | [Z VS Code do vim](prechod-z-ide/B03-vscode.md) | mentální posuny, mapa zkratek, strategie přechodu | ✅ |
| B04 | [Z JetBrains do vim](prechod-z-ide/B04-jetbrains.md) | mapování akcí (Alt+Enter…), IdeaVim jako mezistanice, hybrid | ✅ |
| B05 | [Refaktoring](prechod-z-ide/B05-refaktoring.md) | žebřík: LSP rename/actions → quickfix `:cfdo` → `cgn`; poctivé limity | ✅ |
| B06 | [Git jako GitLens](prechod-z-ide/B06-git.md) | gitsigns (hunky, blame) + lazygit za 60 s + workflow bez opuštění editoru | ✅ |
| B07 | [Multi-file & workspace](prechod-z-ide/B07-workspace.md) | root/projekt, globální marky, sessions, jump list | ✅ |
| B08 | [Autocomplete a snippety](prechod-z-ide/B08-autocomplete.md) | blink.cmp, snippety, inlay hints, AI extras | ✅ |
| B09 | [Debugging](prechod-z-ide/B09-debugging.md) | nvim-dap, launch.json z VS Code, poctivý žebřík | ✅ |

**Track B je kompletní** (B00–B09).

## Track C — Recepty 🚧

Nelineární task taháky ve stylu [A10](lekce/A10-ide-vim-mapa.md): „chci udělat X → tady
je jak". Záměrně **bez číslování** — pořadí drží [index v `recepty/`](recepty/README.md),
soubory se jmenují podle tématu.

| Recept | O čem | Stav |
|--------|-------|------|
| [Surround](recepty/surround.md) | obalování: LazyVim `gsa`/`gsd`/`gsr`, klasika `ys`/`cs`/`ds` | ✅ |
| [Marks, skoky a Flash](recepty/marks-a-jumpy.md) | záložky `mA`, historie skoků, bleskový pohyb | ✅ |
| [Markdown v neovim](recepty/markdown-v-neovim.md) | inline rendering, tabulky, náhled | ✅ |
| Ex příkazy & rozsahy | `:m` (move), `:t` (copy), `:normal`, `:%!sort` — vim jako dávkový editor | 🔜 |
| Makra do hloubky | praktické recepty, rekurzivní makra | 🔜 |
| 50 nejčastějších úkonů | velký task tahák | 🔜 |
| Konfigurace LazyVim | přidat plugin, keymapu, option | 🔜 |
| Nerd Fonts & terminál v nvim | okolní setup, `:terminal` / `Ctrl-/` | 🔜 |

## Jak to roste

Tempo drží autor; lekce přibývají postupně. Track A je páteř, tracky B a C se plní podle
toho, co je nejužitečnější (a nejvyhledávanější). Návrhy vítány přes issues.
