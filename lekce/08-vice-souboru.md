# Lekce 08 — Více souborů: buffery, okna, taby

Cíl: pracovat s víc soubory najednou — otevírat, přepínat, dělit obrazovku. vim tu má tři
pojmy, které se pletou: **buffer** (otevřený soubor v paměti), **okno** (výřez na buffer)
a **tab** (rozložení oken). Pořadí důležitosti přesně takové.

## Buffery — otevřené soubory

| Příkaz | Co |
|--------|-----|
| `:e soubor` | otevři soubor (do nového bufferu) |
| `:ls` | vypiš otevřené buffery |
| `:b {číslo/jméno}` | přepni na buffer (jméno stačí částečné) |
| `:bn` / `:bp` | další / předchozí buffer |
| `:bd` | zavři buffer |
| `Ctrl-^` | přepni na **předchozí** buffer (tam a zpět) |

Historicky se pracovalo přes seznam argumentů: `:next` / `:prev` (`:n` / `:N`) projíždí
soubory, se kterými jsi vim spustil. Dnes se víc používají buffery a fuzzy hledání.

## Okna (splity) — dělení obrazovky

| Příkaz / klávesa | Co |
|------------------|-----|
| `:sp` / `:split` | vodorovný split |
| `:vs` / `:vsplit` | svislý split |
| `Ctrl-w h/j/k/l` | přeskoč do okna vlevo/dolů/nahoru/vpravo |
| `Ctrl-w w` | další okno v kruhu |
| `Ctrl-w q` | zavři okno |
| `Ctrl-w =` | vyrovnej velikosti oken |

## Taby — rozložení oken

| Příkaz / klávesa | Co |
|------------------|-----|
| `:tabnew soubor` | nový tab |
| `gt` / `gT` | další / předchozí tab |
| `{číslo}gt` | skoč na tab číslo |

Pozn.: taby ve vim nejsou „záložky souborů" jako v IDE — jsou to pracovní plochy. Na
přepínání souborů používej spíš buffery + Telescope.

## V LazyVim je to pohodlnější

| Klávesa | Co |
|---------|-----|
| `Space Space` | fuzzy hledání souborů (Telescope) |
| `Space bb` | seznam bufferů |
| `Space bd` | zavři buffer |
| `Ctrl-h/j/k/l` | přeskoč mezi splity (bez `Ctrl-w`) |
| `Shift-h` / `Shift-l` | předchozí / další buffer |

## Cvičení
- [ ] Otevři dva soubory (`nvim a.txt b.txt`), přepínej přes `:bn`/`:bp` a `Ctrl-^`.
- [ ] Rozděl obrazovku `:vs`, přeskoč mezi okny přes `Ctrl-w l` / `Ctrl-w h`.
- [ ] V LazyVim zkus `Space Space` a otevři soubor fuzzy hledáním.

## Co dál
[Lekce 09 — LazyVim navrch](09-lazyvim-navrch.md).
