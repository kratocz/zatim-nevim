# zatim-nevim

> **Not an official vim course.** These are one person's personal notes on learning
> (neo)vim from scratch. The name is a Czech pun: *„zatím nevím"* means *„I don't know
> yet"* — and it hides **vim** inside. 😄

Osobní learning log — moje cesta za ovládáním **vim / neovim / LazyVim** od nuly.
Nejsou to oficiální lekce, je to zápisník, který roste s tím, jak se učím.

## Jak s tímhle repem pracovat

- **[ROADMAP.md](ROADMAP.md)** — kam kurz míří: tři tracky (kurz od nuly, přechod z IDE, recepty).
- **[progress.md](progress.md)** — kde právě jsem, co už umím a co je na řadě.
- **[cheatsheet.md](cheatsheet.md)** — gramatika vim na jednom místě (módy, operátory, pohyby, text objekty).
- **[lekce/](lekce/)** — postupné lekce od přežití k plynulosti (Track A).
- **[cviceni/](cviceni/)** — konkrétní soubory k procvičování zásahů.

Kurz má tři tracky — všechny vypsané níže, podrobný plán v [ROADMAP](ROADMAP.md).

## Lekce

Kurz začíná úplně od nuly — předpokládá jen to, že umíš spustit vim.

### Track A — Kurz od nuly (lineární)

| # | Lekce | O čem |
|---|-------|-------|
| A00 | [Nouzové přežití](lekce/A00-nouzove-preziti.md) | spustit a **hlavně ukončit** vim |
| A01 | [Přežití](lekce/A01-preziti.md) | osm základních věcí |
| A02 | [Tři režimy pořádně](lekce/A02-tri-rezimy.md) | Normal / Insert / Visual |
| A03 | [Pohyb](lekce/A03-pohyb.md) | dostat se kamkoli bez šipek |
| A04 | [Editační gramatika](lekce/A04-gramatika.md) | `operátor + pohyb` — srdce vim |
| A05 | [Kopírování a registry](lekce/A05-kopirovani-registry.md) | yank, put, clipboard |
| A06 | [Hledání a nahrazování](lekce/A06-hledani-a-nahrazovani.md) | `:s`, rozsahy, confirm |
| A07 | [Undo, opakování, makra](lekce/A07-undo-opakovani-makra.md) | `.`, makra, `cgn` |
| A08 | [Více souborů](lekce/A08-vice-souboru.md) | buffery, splity, taby |
| A09 | [LazyVim navrch](lekce/A09-lazyvim-navrch.md) | leader, LSP, Telescope |
| A10 | [IDE → vim mapa](lekce/A10-ide-vim-mapa.md) | referenční tahák z IDE |

### Track B — Přechod z IDE (goal-oriented)

Pro lidi z VS Code / JetBrains: „jak ve vim udělám to, co v IDE dělám takhle".

| # | Lekce | O čem |
|---|-------|-------|
| B00 | [vim uvnitř tvého IDE](prechod-z-ide/B00-vim-uvnitr-ide.md) | VSCodeVim / IdeaVim — gramatika bez opuštění IDE |
| B01 | [Multi-cursor po vimácku](prechod-z-ide/B01-multicursor.md) | `Cmd+D` → `cgn`, visual-block, `:g`, makra |
| B02 | [`:g` global command](prechod-z-ide/B02-global-command.md) | dávková editace „udělej X na každém řádku s Y" |
| B03 | [Z VS Code do vim](prechod-z-ide/B03-vscode.md) | mentální posuny, mapa zkratek, strategie přechodu |
| B04 | [Z JetBrains do vim](prechod-z-ide/B04-jetbrains.md) | mapování akcí, IdeaVim jako mezistanice, hybrid |
| B05 | [Refaktoring](prechod-z-ide/B05-refaktoring.md) | žebřík LSP → textové nástroje, quickfix `:cfdo` |
| B06 | [Git jako GitLens](prechod-z-ide/B06-git.md) | gitsigns + lazygit, hunk workflow, blame |
| B07 | [Multi-file & workspace](prechod-z-ide/B07-workspace.md) | root/projekt, globální marky, sessions |
| B08 | [Autocomplete a snippety](prechod-z-ide/B08-autocomplete.md) | blink.cmp, snippety, inlay hints, AI |
| B09 | [Debugging](prechod-z-ide/B09-debugging.md) | nvim-dap, launch.json, poctivý žebřík |

### Track C — Recepty (nelineární)

Task taháky „chci udělat X → tady je jak"; bez pořadí, skoč na co potřebuješ.

| Recept | O čem |
|--------|-------|
| [Surround](recepty/surround.md) | obal / změň / smaž závorky, uvozovky, tagy |
| [Marks, skoky a Flash](recepty/marks-a-jumpy.md) | záložky (`mA`), historie skoků, bleskový pohyb |
| [Markdown v neovim](recepty/markdown-v-neovim.md) | inline rendering, tabulky, náhled |
| [Ex příkazy a rozsahy](recepty/ex-prikazy.md) | `:m`, `:t`, `:sort`, `:normal`, filtry `:%!` |
| [Makra do hloubky](recepty/makra-do-hloubky.md) | robustní makra, oprava bez přenahrávání, rekurze |
| [50 nejčastějších úkonů](recepty/50-ukonu.md) | velký task tahák |
| [Konfigurace LazyVim](recepty/konfigurace-lazyvim.md) | option, keymapa, plugin |
| [Nerd Fonts a terminál](recepty/nerd-fonts-a-terminal.md) | ikony, true color, terminál v editoru |

## Mentální model v jedné větě

Vim není editor s divnými zkratkami — je to **malý jazyk**, kde skládáš věty
`operátor + pohyb` (např. `d` + `w` = `dw` = smaž slovo). Jakmile cvakne gramatika,
zbytek si odvodíš sám.

---

*Repo je záměrně pojmenované tak, aby si ho nikdo nespletl s autoritativním zdrojem.
Když hledáš opravdové lekce, začni vestavěným `vimtutor`.*

## Licence

Obsah je pod licencí [CC BY 4.0](LICENSE) — sdílej a upravuj libovolně (i komerčně),
jen uveď autora (Petr Kratochvíl, [kratocz/zatim-nevim](https://github.com/kratocz/zatim-nevim))
a vyznač případné změny.
