# Postup

Kde jsem na cestě za vim. Odškrtávám, jak jdu. Každá položka odkazuje na lekci.

## [00 — Nouzové přežití](lekce/00-nouzove-preziti.md)
- [ ] Spustit `nvim`, `Esc` jako záchrana
- [ ] Ukončit: `:q` `:q!` `:wq` `ZZ`

## [01 — Přežití](lekce/01-preziti.md)
- [ ] `h j k l`, `i` / `Esc`, `:w` / `:q`, `x`, `dd`, `u`

## [02 — Tři režimy](lekce/02-tri-rezimy.md)
- [ ] Rozlišit Normal / Insert / Visual
- [ ] Vstupy do Insertu: `i a I A o O`
- [ ] Visual: `v V Ctrl-v`

## [03 — Pohyb](lekce/03-pohyb.md)
- [ ] Po řádku: `0 ^ $`, `w b e`, `f t ; ,`
- [ ] Po souboru: `gg G`, `{n}G` / `:{n}`, `{ }`, `Ctrl-d/u`
- [ ] Count: `3w`, `5j`

## [04 — Editační gramatika](lekce/04-gramatika.md)
- [ ] Operátory `d c y > =`
- [ ] Text objekty `iw i( i" ip it`
- [ ] Skládání: `ciw`, `di(`, `dt,`, `>ip`
- [ ] Zdvojení `dd yy cc`, tečka `.`

## [05 — Kopírování a registry](lekce/05-kopirovani-registry.md)
- [ ] `yy dd p P`
- [ ] Pojmenované registry `"ayy` / `"ap`, yank registr `"0p`
- [ ] Systémová schránka `"+y` / `"+p`

## [06 — Hledání a nahrazování](lekce/06-hledani-a-nahrazovani.md)
- [ ] Hledání `/ ?`, `n N`, `* #`, `:noh`
- [ ] Rozsahy `:%`, `:10,20`, `:.,+5`, `:'<,'>`
- [ ] Flagy `g`, **`c` (confirm)**, `i`
- [ ] `:%s/x/y/gc` s `y n a q`

## [07 — Undo, opakování, makra](lekce/07-undo-opakovani-makra.md)
- [ ] `u` / `Ctrl-r`, opakování `.`
- [ ] Makra `qa … q`, `@a`, `5@a`
- [ ] Multi-cursor po vimácku `cgn` + `.`

## [08 — Více souborů](lekce/08-vice-souboru.md)
- [ ] Buffery `:e :ls :b :bn :bp`, `Ctrl-^`
- [ ] Splity `:vs :sp`, `Ctrl-w h/j/k/l`
- [ ] Taby `:tabnew`, `gt gT`

## [09 — LazyVim navrch](lekce/09-lazyvim-navrch.md)
- [ ] Leader `Space` + which-key
- [ ] Telescope `Space Space`, grep `Space /`, file tree `Space e`
- [ ] LSP `gd gr K`, rename `Space cr`, code action `Space ca`
- [ ] `:LazyExtras` (např. `lang.markdown`)

## [10 — IDE → vim mapa](lekce/10-ide-vim-mapa.md)
- [ ] Projít referenční tahák

## Poznámky
<!-- Sem si píšu, co mi nešlo, co mi cvaklo, na co se zeptat příště. -->
