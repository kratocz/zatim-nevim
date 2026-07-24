# Recept — Nerd Fonts a terminál

LazyVim (which-key, file tree, lazygit, render-markdown…) kreslí ikony ze speciálních
znaků. Bez **Nerd Fontu** uvidíš čtverečky — tenhle recept dává do pořádku okolí editoru.

## Instalace fontu

**macOS (Homebrew):**
```bash
brew install --cask font-jetbrains-mono-nerd-font   # nebo font-meslo-lg-nerd-font
```

**Linux:** balíček distribuce, nebo stáhni z [nerdfonts.com](https://www.nerdfonts.com/)
a nakopíruj do `~/.local/share/fonts` + `fc-cache -f`.

## Nastavení v terminálu

Font je věc **terminálu**, ne vimu:

| Terminál | Kde |
|----------|-----|
| iTerm2 | Settings → Profiles → Text → Font → „JetBrainsMono Nerd Font" |
| Terminal.app | Settings → Profiles → Font |
| kitty / ghostty / WezTerm | `font_family JetBrainsMono Nerd Font` v configu |

**tmux:** nic nenastavuješ — font řeší terminál pod ním. ✔️

## True color (24bit barvy)

Ať barevná schémata vypadají, jak mají. Moderní terminály umí rovnou; **v tmuxu** přidej
do `~/.tmux.conf` (podle verze tmuxu):

```tmux
set -as terminal-features ",xterm-256color:RGB"
```

Ověření: `:checkhealth` v nvim si na truecolor a další věci postěžuje sám.

## Terminál uvnitř editoru

| Klávesy | Co |
|---------|-----|
| `Ctrl+/` | otevři/zavři terminál (LazyVim) |
| `Esc Esc` | z psaní v terminálu zpět do Normal módu |
| `:terminal` | terminál v aktuálním okně (čistý nvim) |

Rychlá smyčka „edituj → spusť → zpět" bez opouštění editoru; hodí se i pro
print-debugging z [B09](../prechod-z-ide/B09-debugging.md).

## Kontrola, že je vše OK

- [ ] `:checkhealth` — bez červených chyb u UI/truecolor.
- [ ] `Space e` — file tree má ikony souborů, ne čtverečky.
- [ ] `Space gg` — lazygit vypadá vzhledně (rámečky, symboly větví).

## Cvičení
- [ ] Nainstaluj Nerd Font a nastav ho v terminálu.
- [ ] (tmux) Přidej truecolor řádek a restartuj server (`tmux kill-server` v klidnou chvíli).
- [ ] `Ctrl+/` → spusť něco → `Esc Esc` → `q` zpět do editoru.
