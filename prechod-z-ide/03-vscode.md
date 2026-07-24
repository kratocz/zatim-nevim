# B3 — Z VS Code do vim

Pro lidi, co roky žijí ve VS Code a chtějí (aspoň zkusit) plný neovim s LazyVim. Cíl:
přemapovat svalovou paměť, ne se učit „všechno znovu". Pokud zatím nechceš VS Code
opouštět, začni [lekcí B0](00-vim-uvnitr-ide.md) — vim mód uvnitř VS Code.

> Zkratky uvádím v macOS podobě (`Cmd`); na Windows/Linuxu čti `Ctrl`.

## Změna myšlení — čtyři posuny

1. **Command Palette → `Space`.** Ve VS Code je bránou ke všemu `Cmd+Shift+P`. V LazyVim
   zmáčkni `Space` a **čti** which-key nabídku. A `Space sk` je „paleta zkratek" —
   fuzzy hledání v klávesových mapách (nevíš-li, jak se něco dělá, najdeš to tam).
2. **Taby → buffery.** VS Code taby = otevřené soubory. Ve vim jsou otevřené soubory
   buffery (`Shift-h` / `Shift-l` přepíná) a taby jsou něco jiného ([lekce 08](../lekce/08-vice-souboru.md)).
3. **settings.json → Lua; Marketplace → `:Lazy`.** Konfigurace jsou soubory v
   `~/.config/nvim/lua/`, pluginy spravuje `:Lazy`, kurátorované balíčky `:LazyExtras`.
4. **Autosave není default.** Zvykni si na `:w` — ale dobrá zpráva: LazyVim má
   namapované **`Ctrl+S`**, takže ukládání funguje postaru. A schránka je sdílená se
   systémem out-of-box (`y`/`p` = normální copy/paste).

## Mapa zkratek VS Code → LazyVim

### Navigace a hledání
| VS Code | LazyVim |
|---------|---------|
| `Cmd+P` (Quick Open) | `Space Space` |
| `Cmd+Shift+P` (Command Palette) | `Space` (which-key), `:` příkazy, `Space sk` (hledej zkratku) |
| `Cmd+Shift+F` (hledej v projektu) | `Space /` (live grep) |
| `Cmd+F` (hledej v souboru) | `/vzor`, pak `n` / `N` |
| `Cmd+Shift+O` (symbol v souboru) | `Space ss` |
| `Cmd+T` (symbol v projektu) | `Space sS` |
| `F12` (definice) / `Shift+F12` (reference) | `gd` / `gr` (zpět `Ctrl-o`) |
| `F8` (další problém) | `]d` / `[d`; přehled `Space xx` (Trouble) |
| `Ctrl+Tab` (přepni editor) | `Shift-l` / `Shift-h` |

### Editace
| VS Code | LazyVim |
|---------|---------|
| `Cmd+D` (další výskyt, multi-cursor) | `*` → `cgn` → `.` / `n` — viz [B1](01-multicursor.md) |
| `Cmd+/` (komentář) | `gcc`, ve Visualu `gc` |
| `F2` (rename symbol) | `Space cr` |
| `Cmd+.` (Quick Fix) | `Space ca` |
| `Shift+Alt+F` (formátuj) | `Space cf` |
| `Alt+↓` / `Alt+↑` (přesuň řádek) | `Alt-j` / `Alt-k` (stejný pocit!) |
| `Shift+Alt+↓` (duplikuj řádek) | `yyp` |
| `Cmd+X` (vyjmi řádek) | `dd` |
| `Cmd+A` (označ vše) | `ggVG` |
| `Cmd+S` / uložit vše | `Ctrl+S` nebo `:w` / `:wa` |

### Okolí editoru
| VS Code | LazyVim |
|---------|---------|
| `Cmd+B` (sidebar) | `Space e` (file tree) |
| ``Ctrl+` `` (terminál) | `Ctrl+/` |
| `Cmd+W` (zavři editor) | `Space bd` |
| Source Control / GitLens | `Space gg` (lazygit), hunky `]h` / `[h` |
| `Cmd+Shift+V` (Markdown preview) | Extra `lang.markdown` — renderuje přímo v bufferu |
| Reopen po startu | `Space qs` (obnov session) |
| `F5` (debug) | nvim-dap (Extras `dap.core`) — viz „poctivě" níže |

## Poctivě: co ti bude chybět

- **Debugger UI out-of-box.** nvim-dap funguje, ale nastavení je práce. Klidně si na
  debugování nech VS Code, dokud dap nedoladíš — hybrid není selhání.
- **Live Share** nemá plnohodnotný ekvivalent.
- **Šíře marketplace** — neovim ekosystém je velký, ale ne *takhle* velký.

## Co získáš

- **Odezvu a RAM** — start v milisekundách, žádný Electron.
- **SSH bez mostu** — na serveru prostě spustíš `nvim`; žádný Remote-SSH, stejný editor
  všude (a vim gramatika funguje i v holém `vi` na jakémkoli stroji).
- **Skládatelnost** — gramatika ([lekce 04](../lekce/04-gramatika.md)) × LSP × Telescope
  se navzájem násobí.

## Strategie přechodu (doporučené fáze)

1. **VSCodeVim ve VS Code** ([B0](00-vim-uvnitr-ide.md)) + Track A lekce 02–07 — gramatika v bezpečí.
2. **LazyVim na nízkorizikové věci** — poznámky, configy, Markdown.
3. **Projekty bez debuggeru** — zapni `:LazyExtras` pro svůj jazyk.
4. **Full-time**, VS Code drž jako debugger, dokud nedáš nvim-dap.

## Cvičení
- [ ] Otevři svůj reálný projekt: `Space Space` (soubor), `Space /` (grep), `gd` + `Ctrl-o`.
- [ ] Přes `Space sk` najdi zkratku, kterou neznáš.
- [ ] `Ctrl+/` terminál, `Space gg` lazygit.
- [ ] Projeď find&replace flow: `:%s/x/y/gc` ([lekce 06](../lekce/06-hledani-a-nahrazovani.md)).

## Co dál
[B4 — Z JetBrains do vim](04-jetbrains.md) pro kolegy z druhého tábora, nebo zpět na
[index Tracku B](README.md).
