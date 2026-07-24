# B4 — Z JetBrains do vim (IntelliJ, PyCharm, WebStorm…)

JetBrains člověk nemyslí ve zkratkách, ale v **akcích**: Search Everywhere, Alt+Enter,
Rename, Extend Selection. Proto tuhle lekci vedu přes akce — u každé najdeš LazyVim
ekvivalent. A protože **IdeaVim** je výjimečně kvalitní (oficiální plugin od JetBrains),
věnuju mu vlastní sekci: pro spoustu lidí je to nejdelší, klidně trvalá mezistanice.

> Zkratky uvádím v macOS podobě; kde se Windows liší zásadně, uvádím obě.

## IdeaVim — plnohodnotná mezistanice

Instalaci řeší [lekce B0](00-vim-uvnitr-ide.md). Tady power tipy do `~/.ideavimrc`, které
z IdeaVim udělají víc než emulaci:

```vim
let mapleader=" "                        " Space jako leader (jako LazyVim)
map <leader>r <Action>(RenameElement)    " leader mapy na IDE akce
map <leader>ca <Action>(ShowIntentionActions)
set surround commentary which-key        " emulované vim pluginy
set ideajoin                             " chytré J (spojí řetězce, komentáře…)
sethandler <C-d> a:vim                   " konflikt Ctrl kláves: kdo klávesu dostane
```

- **`:actionlist vzor`** — vypíše ID akcí IDE (co jde namapovat přes `<Action>(…)`).
- Emulace zvládá gramatiku, text objekty, makra, `:s`, `:g` — celý Track A.

## Mapa akcí JetBrains → LazyVim

### Navigace a hledání
| Akce (zkratka) | LazyVim |
|----------------|---------|
| Search Everywhere (`2× Shift`) | `Space Space` soubory, `Space ss` symboly, `Space /` text, `Space sk` klávesy |
| Go to Class / File / Symbol (`Cmd+O` / `Cmd+Shift+O` / `Cmd+Alt+O`) | `Space Space` / `Space ss` / `Space sS` |
| Recent Files (`Cmd+E`) | `Space ,` (buffery), `Space fr` (nedávné) |
| Go to Declaration (`Cmd+B`) | `gd` (zpět `Ctrl-o`) |
| Go to Implementation (`Cmd+Alt+B`) | `gI` |
| Find Usages (`Alt+F7`) | `gr` |
| Quick Documentation (`F1` / win `Ctrl+Q`) | `K` |
| File Structure (`Cmd+F12`) | `Space ss` |
| Next / Prev Error (`F2` / `Shift+F2`) | `]d` / `[d`; přehled `Space xx` |
| Find in Path (`Cmd+Shift+F`) | `Space /` |
| Replace in Path (`Cmd+Shift+R`) | `Space sr` (projektový find&replace), per-soubor `:%s/…/…/gc` |

### Editace a refaktoring
| Akce (zkratka) | LazyVim |
|----------------|---------|
| **Intention Actions (`Alt+Enter`)** ⭐ | **`Space ca`** (code action) |
| Rename (`Shift+F6`) | `Space cr` |
| Reformat Code (`Cmd+Alt+L`) | `Space cf` |
| **Extend / Shrink Selection (`Alt+↑`/`Alt+↓`, win `Ctrl+W`/`Ctrl+Shift+W`)** ⭐ | **`Ctrl-Space`** rozšiřuje, **`Backspace`** zužuje (Treesitter) |
| Comment (`Cmd+/`) | `gcc`, ve Visualu `gc` |
| Duplicate Line (`Cmd+D` — pozor, ve VS Code je to multi-cursor!) | `yyp` |
| Delete Line (`Cmd+Backspace`) | `dd` |
| Move Line (`Alt+Shift+↑/↓`) | `Alt-k` / `Alt-j` |
| Add Selection for Next Occurrence (`Ctrl+G`, win `Alt+J`) | `*` → `cgn` → `.` / `n` — viz [B1](01-multicursor.md) |

### Okolí
| Akce (zkratka) | LazyVim |
|----------------|---------|
| Commit (`Cmd+K`) / Git tool window (`Cmd+9`) | `Space gg` (lazygit); hunky `]h` / `[h` |
| Bookmarks (`F3`) | marks: `ma` nastaví, `` `a `` skočí (lekce v Tracku C 🔜) |
| Terminál (`Alt+F12`) | `Ctrl+/` |
| Run / Debug | nvim-dap (Extras) — viz „poctivě" níže |

## Poctivě: co JetBrains umí líp

- **Hluboké refaktoringy** — Change Signature, Move, Extract Interface… stojí na vlastním
  sémantickém indexu. LSP svět dává spolehlivě rename + code actions; hlubší přestavby
  závisí na konkrétním language serveru (jazyk od jazyka).
- **Debugger, DB tools, framework magie** (Spring, …) — integrované a vyladěné.

**Co získáš:** odezvu a RAM (IDEA si ráda vezme gigabajty), start v milisekundách, stejný
editor na serveru přes ssh a gramatiku, která funguje všude.

## Doporučený hybrid (bez dogmat)

- **Těžké refaktorovací dny** (Java/Kotlin): IDEA + IdeaVim — svalová paměť vim zůstává.
- **Všechno ostatní** (poznámky, skripty, configy, commity, servery): LazyVim.
- Klíč: vim gramatiku se učíš **jednou** a používáš v obou světech. Nic se nezmarní.

## Cvičení
- [ ] Do `~/.ideavimrc` přidej leader mapy a `set surround`; ověř `:actionlist Rename`.
- [ ] V LazyVim projdi: `Space ,`, `gd`, `gI`, `gr`, `K`, `Space ca`, `Space cr`.
- [ ] Vyzkoušej `Ctrl-Space` / `Backspace` (extend/shrink selection) na reálném kódu.

## Co dál
[B5 — Refaktoring](05-refaktoring.md), nebo zpět na [index Tracku B](README.md).
