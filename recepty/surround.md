# Recept — Surround: obal, změň, smaž

Denní chleba: dát slovo do uvozovek, změnit `"` na `'`, smazat závorky kolem výrazu,
obalit výběr HTML tagem. V IDE na to sahá myš; tady je to pár úhozů.

## V LazyVim (mini.surround, prefix `gs`)

| Akce | Klávesy | Příklad |
|------|---------|---------|
| Přidej obal | `gsa{objekt}{znak}` | `gsaiw"` → slovo → `"slovo"` |
| Smaž obal | `gsd{znak}` | `gsd"` → `"slovo"` → slovo |
| Změň obal | `gsr{starý}{nový}` | `gsr"'` → `"slovo"` → `'slovo'` |
| Z výběru | označ (`v`/`V`) → `gsa{znak}` | výběr → `gsa)` → `(výběr)` |
| HTML tag | `gsat` a zadej název tagu | slovo → `<b>slovo</b>` |

Drobnost, která překvapí: **zavírací** znak (`)`, `}`, `]`) obalí těsně, **otevírací**
(`(`, `{`, `[`) přidá i mezery: `gsaiw)` → `(slovo)`, ale `gsaiw(` → `( slovo )`.

Nemusíš si to pamatovat: zmáčkni `gs` a which-key nabídka ti zbytek připomene.

## Klasika `ys` / `cs` / `ds` (vim-surround)

Mimo LazyVim se používá schéma z pluginu tpope/vim-surround — **VSCodeVim ho má
vestavěné**, IdeaVim přes `set surround` (viz [B00](../prechod-z-ide/B00-vim-uvnitr-ide.md)):

| Akce | Klávesy | Příklad |
|------|---------|---------|
| Přidej | `ys{objekt}{znak}` | `ysiw"` |
| Smaž | `ds{znak}` | `ds"` |
| Změň | `cs{starý}{nový}` | `cs"'` |
| Z výběru | `S{znak}` ve Visualu | `V` → `S<p>` |

Logika je totožná, jen jiný prefix — naučíš se jedno, druhé je transliterace.

## Cvičení
Otevři `../cviceni/surround.txt`:
- [ ] Obal slovo do uvozovek (`gsaiw"`) a zase je smaž (`gsd"`).
- [ ] Změň `"` na `'` (`gsr"'`) a `(` na `[` (`gsr([`).
- [ ] Označ řádek `V` a obal ho do tagu `<p>` (`gsat`).
