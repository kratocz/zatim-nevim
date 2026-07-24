# Recept — Marks, skoky a Flash

Jak se ve velkém projektu neztratit: záložky (marky), historie skoků a bleskový pohyb
po obrazovce. Ekvivalent bookmarků a AceJump/EasyMotion z IDE.

## Marky = záložky

| Klávesy | Co |
|---------|-----|
| `ma` | nastav mark `a` (malá písmena = lokální v souboru) |
| `` `a `` | skoč přesně na něj (`'a` = na začátek jeho řádku) |
| **`mA`–`mZ`** | **globální marky — fungují napříč soubory** ⭐ |
| `:marks` / `Space sm` | přehled / picker |
| `:delmarks a` / `:delmarks!` | smaž mark / všechny lokální |

Workflow „tři rozdělaná místa": `mA` na modelu, `mB` na endpointu, `mC` na testu — a pak
se mezi nimi přepínáš `` `A `` / `` `B `` / `` `C `` na dva úhozy, klidně napříč soubory.
Rychlejší než bookmarky v IDE: žádné UI, žádná myš.

## Automatické marky (nastavuje vim sám)

| Klávesy | Skočí |
|---------|-------|
| `` `` `` | tam, kde jsi byl před posledním skokem (tam-a-zpět) |
| `` `. `` | na místo poslední změny |
| `` `^ `` | na místo posledního psaní (Insert) |

## Historie skoků

| Klávesy | Co |
|---------|-----|
| `Ctrl-o` / `Ctrl-i` | jump list zpět / vpřed — **napříč soubory** (Back/Forward z IDE) |
| `g;` / `g,` | change list — po místech, kde jsi naposledy editoval |

## Flash: pohyb „kliknutím klávesnice"

LazyVim má flash.nvim: zmáčkni **`s`** + dva znaky cíle a doskočíš štítkem kamkoli na
obrazovce. Ekvivalent AceJump / EasyMotion (v IdeaVim: `set easymotion`). Funguje i
s operátorem: `d` + `s` + cíl smaže přesně po tam.

## Cvičení
- [ ] Ve dvou souborech nastav `mA` a `mB` a přepínej se `` `A `` / `` `B ``.
- [ ] Skoč `gd` na definici a vrať se `` `` `` (dva backticky).
- [ ] `s` + dva znaky viditelného slova — doskoč štítkem.
- [ ] Po delší editaci zkus `g;` — vrátí tě k poslednímu zásahu.
