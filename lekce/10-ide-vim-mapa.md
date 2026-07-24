# Lekce 10 — IDE → vim mapa

Referenční tahák pro přechod z IDE (VS Code, JetBrains…). Když víš, jak se něco jmenuje
v IDE, tady najdeš vimácký ekvivalent. `Space` = LazyVim leader.

## Navigace

| IDE | vim / LazyVim |
|-----|---------------|
| Goto line | `:42` nebo `42G` |
| Go to file | `Space Space` (Telescope) |
| Go to symbol / definition | `gd` |
| Find references | `gr` |
| Back / Forward | `Ctrl-o` / `Ctrl-i` |
| Go to matching bracket | `%` |

## Hledání a nahrazování

| IDE | vim / LazyVim |
|-----|---------------|
| Find in file | `/text` (další `n`, předchozí `N`) |
| Find word under cursor | `*` / `#` |
| Replace (s tlačítky Replace/Skip/All) | `:%s/x/y/gc` → `y` / `n` / `a` |
| Replace in selection | `V` výběr → `:'<,'>s/x/y/g` |
| Find in project (grep) | `Space /` |

## Editace

| IDE | vim / LazyVim |
|-----|---------------|
| Undo / Redo | `u` / `Ctrl-r` |
| Cut / Copy / Paste | `d` / `y` / `p` |
| Select all | `ggVG` |
| Select line | `V` |
| Duplicate line | `yyp` |
| Delete line | `dd` |
| Move line up / down | `:m` (LazyVim `Alt-j` / `Alt-k`) |
| Comment line / selection | `gcc` / `gc` |
| Rename symbol | `Space cr` |
| Format document | `Space cf` |
| Multi-cursor | `*` → `cgn` → `.` / `n` (viz [lekce 07](07-undo-opakovani-makra.md)) |

## Soubory a okna

| IDE | vim / LazyVim |
|-----|---------------|
| Open file explorer | `Space e` |
| Split editor (vertical) | `:vs` |
| Switch tab / buffer | `Shift-l` / `Shift-h` |
| Close tab / buffer | `Space bd` |
| Save / Save all | `:w` / `:wa` |

## Ostatní

| IDE | vim / LazyVim |
|-----|---------------|
| Command palette | `Space` (which-key) nebo `:` |
| Quick fix / code action | `Space ca` |
| Next / prev problem | `]d` / `[d` |
| Git panel | `Space gg` (lazygit) |
| Documentation on hover | `K` |

## Co dál

Chceš jít hlouběji? Pokračuj [Trackem B — Přechod z IDE](../prechod-z-ide/README.md):
vim přímo uvnitř VS Code / JetBrains, multi-cursor po vimácku, `:g` global command.

---

Když si nevíš rady: **`Esc` tě vrátí do klidu a `Space` ukáže, co dál.** Zbytek je praxe. 🚀
