# Postup

Kde jsem na cestě za vim. Odškrtávám, jak jdu. Každá položka odkazuje na lekci.

## [A00 — Nouzové přežití](lekce/A00-nouzove-preziti.md)
- [ ] Spustit `nvim`, `Esc` jako záchrana
- [ ] Ukončit: `:q` `:q!` `:wq` `ZZ`

## [A01 — Přežití](lekce/A01-preziti.md)
- [ ] `h j k l`, `i` / `Esc`, `:w` / `:q`, `x`, `dd`, `u`

## [A02 — Tři režimy](lekce/A02-tri-rezimy.md)
- [ ] Rozlišit Normal / Insert / Visual
- [ ] Vstupy do Insertu: `i a I A o O`
- [ ] Visual: `v V Ctrl-v`

## [A03 — Pohyb](lekce/A03-pohyb.md)
- [ ] Po řádku: `0 ^ $`, `w b e`, `f t ; ,`
- [ ] Po souboru: `gg G`, `{n}G` / `:{n}`, `{ }`, `Ctrl-d/u`
- [ ] Count: `3w`, `5j`

## [A04 — Editační gramatika](lekce/A04-gramatika.md)
- [ ] Operátory `d c y > =`
- [ ] Text objekty `iw i( i" ip it`
- [ ] Skládání: `ciw`, `di(`, `dt,`, `>ip`
- [ ] Zdvojení `dd yy cc`, tečka `.`

## [A05 — Kopírování a registry](lekce/A05-kopirovani-registry.md)
- [ ] `yy dd p P`
- [ ] Pojmenované registry `"ayy` / `"ap`, yank registr `"0p`
- [ ] Systémová schránka `"+y` / `"+p`

## [A06 — Hledání a nahrazování](lekce/A06-hledani-a-nahrazovani.md)
- [ ] Hledání `/ ?`, `n N`, `* #`, `:noh`
- [ ] Rozsahy `:%`, `:10,20`, `:.,+5`, `:'<,'>`
- [ ] Flagy `g`, **`c` (confirm)**, `i`
- [ ] `:%s/x/y/gc` s `y n a q`

## [A07 — Undo, opakování, makra](lekce/A07-undo-opakovani-makra.md)
- [ ] `u` / `Ctrl-r`, opakování `.`
- [ ] Makra `qa … q`, `@a`, `5@a`
- [ ] Multi-cursor po vimácku `cgn` + `.`

## [A08 — Více souborů](lekce/A08-vice-souboru.md)
- [ ] Buffery `:e :ls :b :bn :bp`, `Ctrl-^`
- [ ] Splity `:vs :sp`, `Ctrl-w h/j/k/l`
- [ ] Taby `:tabnew`, `gt gT`

## [A09 — LazyVim navrch](lekce/A09-lazyvim-navrch.md)
- [ ] Leader `Space` + which-key
- [ ] Telescope `Space Space`, grep `Space /`, file tree `Space e`
- [ ] LSP `gd gr K`, rename `Space cr`, code action `Space ca`
- [ ] `:LazyExtras` (např. `lang.markdown`)

## [A10 — IDE → vim mapa](lekce/A10-ide-vim-mapa.md)
- [ ] Projít referenční tahák

---

## Track B — [Přechod z IDE](prechod-z-ide/README.md)

### [B00 — vim uvnitř IDE](prechod-z-ide/B00-vim-uvnitr-ide.md)
- [ ] Nainstalovat VSCodeVim / IdeaVim, namapovat `jk` → `Esc`
- [ ] Zapnout `relativenumber` a zkusit `5j` / `3k`

### [B01 — Multi-cursor po vimácku](prechod-z-ide/B01-multicursor.md)
- [ ] `*` → `cgn` + `.` / `n`
- [ ] Visual block: `Ctrl-v` + `I` / `$ A` / `c`
- [ ] Vědět, kdy sáhnout po `:g` a kdy po makru (rozhodovací tabulka)

### [B02 — :g global command](prechod-z-ide/B02-global-command.md)
- [ ] `:g/vzor/d`, `:v/vzor/d`
- [ ] `:g/vzor/m$`, `:g/vzor/t$`
- [ ] `:g/./normal A;`

### [B03 — Z VS Code do vim](prechod-z-ide/B03-vscode.md)
- [ ] `Space sk` jako „paleta zkratek", projít mapu zkratek
- [ ] Naplánovat fáze přechodu (VSCodeVim → LazyVim na poznámky → projekty)

### [B04 — Z JetBrains do vim](prechod-z-ide/B04-jetbrains.md)
- [ ] `.ideavimrc`: leader + `<Action>(…)` mapy, `set surround`
- [ ] LazyVim ekvivalenty: `Space ca` (Alt+Enter), `Ctrl-Space` (extend selection)

### [B05 — Refaktoring](prechod-z-ide/B05-refaktoring.md)
- [ ] `Space cr` rename + kontrola přes `gr`
- [ ] Visual výběr → `Space ca` → Extract (co umí můj server?)
- [ ] Quickfix recept: `Space /` → `Ctrl-q` → `:cfdo %s/…/…/gc | update`

### [B06 — Git jako GitLens](prechod-z-ide/B06-git.md)
- [ ] Hunk workflow: `]h` → `Space ghp` → `Space ghs` / `Space ghu`
- [ ] Blame `Space gb`, otevřít na GitHubu `Space gB`
- [ ] lazygit: `Space gg`, stage `Space`, commit `c`, push `P`, nápověda `?`

### [B07 — Multi-file & workspace](prechod-z-ide/B07-workspace.md)
- [ ] Globální marky `mA`/`mB` napříč soubory, picker `Space sm`
- [ ] `Ctrl-o`/`Ctrl-i` napříč soubory, session `Space qs`

### [B08 — Autocomplete a snippety](prechod-z-ide/B08-autocomplete.md)
- [ ] `Ctrl-Space` / `Ctrl-n` / `Ctrl-p` / `Enter` / `Ctrl-e`
- [ ] Snippet + `Tab`/`S-Tab`, inlay hints `Space uh`

### [B09 — Debugging](prechod-z-ide/B09-debugging.md)
- [ ] Zapnout `dap.core` + jazykový Extra
- [ ] `Space db` / `dc` / `dO` / `du` / `dw` na malém skriptu

---

## Track C — [Recepty](recepty/README.md)

### [Surround](recepty/surround.md)
- [ ] `gsaiw"`, `gsd"`, `gsr"'` (LazyVim) / `ysiw"`, `ds"`, `cs"'` (klasika)

### [Marks, skoky a Flash](recepty/marks-a-jumpy.md)
- [ ] Globální marky `mA`/`mB` napříč soubory, picker `Space sm`
- [ ] Flash: `s` + dva znaky cíle

### [Markdown v neovim](recepty/markdown-v-neovim.md)
- [ ] Zapnout `lang.markdown`, prohlédnout cheatsheet, `Space ss` osnova

### [Ex příkazy a rozsahy](recepty/ex-prikazy.md)
- [ ] `:t.` / `:m$`, `:'<,'>sort u`
- [ ] Filtr `:'<,'>!column -t`, `:'<,'>normal A;`

### [Makra do hloubky](recepty/makra-do-hloubky.md)
- [ ] Makro na výběr přes `:'<,'>normal @a`
- [ ] Oprava makra jako textu (`"ap` → edit → `0"ay$`)
- [ ] Rekurzivní makro (`qaq` → `qa … @a q`)

### [50 nejčastějších úkonů](recepty/50-ukonu.md)
- [ ] Projít tahák; označit si, co ještě nemám v prstech

### [Konfigurace LazyVim](recepty/konfigurace-lazyvim.md)
- [ ] Vlastní keymapa s `desc`, plugin přes spec, oprava `opts`

### [Nerd Fonts a terminál](recepty/nerd-fonts-a-terminal.md)
- [ ] Nerd Font v terminálu, `:checkhealth` čistý, `Ctrl+/` smyčka

## Poznámky
<!-- Sem si píšu, co mi nešlo, co mi cvaklo, na co se zeptat příště. -->
