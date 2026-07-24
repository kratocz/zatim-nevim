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

Kurz má tři tracky (viz [ROADMAP](ROADMAP.md)): **A — Kurz od nuly** (lineární, níže),
**[B — Přechod z IDE](prechod-z-ide/)** (goal-oriented pro lidi z VS Code / JetBrains;
hotové B0–B2), **C — Recepty** (task taháky, plánováno).

## Lekce

Kurz začíná úplně od nuly — předpokládá jen to, že umíš spustit vim.

| # | Lekce | O čem |
|---|-------|-------|
| 00 | [Nouzové přežití](lekce/00-nouzove-preziti.md) | spustit a **hlavně ukončit** vim |
| 01 | [Přežití](lekce/01-preziti.md) | osm základních věcí |
| 02 | [Tři režimy pořádně](lekce/02-tri-rezimy.md) | Normal / Insert / Visual |
| 03 | [Pohyb](lekce/03-pohyb.md) | dostat se kamkoli bez šipek |
| 04 | [Editační gramatika](lekce/04-gramatika.md) | `operátor + pohyb` — srdce vim |
| 05 | [Kopírování a registry](lekce/05-kopirovani-registry.md) | yank, put, clipboard |
| 06 | [Hledání a nahrazování](lekce/06-hledani-a-nahrazovani.md) | `:s`, rozsahy, confirm |
| 07 | [Undo, opakování, makra](lekce/07-undo-opakovani-makra.md) | `.`, makra, `cgn` |
| 08 | [Více souborů](lekce/08-vice-souboru.md) | buffery, splity, taby |
| 09 | [LazyVim navrch](lekce/09-lazyvim-navrch.md) | leader, LSP, Telescope |
| 10 | [IDE → vim mapa](lekce/10-ide-vim-mapa.md) | referenční tahák z IDE |

## Mentální model v jedné větě

Vim není editor s divnými zkratkami — je to **malý jazyk**, kde skládáš věty
`operátor + pohyb` (např. `d` + `w` = `dw` = smaž slovo). Jakmile cvakne gramatika,
zbytek si odvodíš sám.

---

*Repo je záměrně pojmenované tak, aby si ho nikdo nespletl s autoritativním zdrojem.
Když hledáš opravdové lekce, začni vestavěným `vimtutor`.*
