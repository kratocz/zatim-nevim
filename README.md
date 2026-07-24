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
kompletní B00–B09), **[C — Recepty](recepty/)** (task taháky, 8 receptů).

## Lekce

Kurz začíná úplně od nuly — předpokládá jen to, že umíš spustit vim.

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
