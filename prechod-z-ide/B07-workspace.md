# B07 — Multi-file & workspace

Jak v LazyVim funguje to, čemu IDE říká „projekt": strom souborů, rychlé otevírání,
hledání napříč projektem, přepínání souborů a návraty tam, kde jsi byl. Základy bufferů
a oken učí [lekce A08](../lekce/A08-vice-souboru.md) — tady jde o workflow navrch.

## Mentální model: projekt = adresář + root

Žádné „workspace soubory". Projekt otevřeš tak, že v jeho adresáři spustíš `nvim`.
LazyVim si sám určí **root** (podle gitu / LSP) a pickery pak hledají v projektu,
ne po celém disku. Monorepo funguje — root se pozná per soubor.

## Soubory a projekty

| V IDE | LazyVim |
|-------|---------|
| Otevřít projekt | `cd projekt && nvim` |
| Znovuotevřít, jak jsem skončil | `Space qs` (obnoví session: buffery, okna) |
| Recent projects | Extra `util.project` → `Space fp` |
| File tree | `Space e`; ve stromu: `a` nový, `r` přejmenuj, `d` smaž, `?` nápověda |
| Rychlé otevření souboru | `Space Space`; nedávné `Space fr`; otevřené `Space ,` |
| Hledání v projektu | `Space /`; slovo pod kurzorem `Space sw` |
| Přepínání souborů | `Shift-h` / `Shift-l`; tam-a-zpět `Ctrl-^` |
| Zavřít soubor / zavřít ostatní | `Space bd` / `Space bo` |
| Split editor | `Space \|` (svisle) / `Space -` (vodorovně); pohyb `Ctrl-h/j/k/l` |

## Navigace historií (Back / Forward)

| V IDE | LazyVim |
|-------|---------|
| Back / Forward | `Ctrl-o` / `Ctrl-i` — jump list, funguje **napříč soubory** |
| Poslední místo změny | `g;` (starší) / `g,` (novější) |
| Bookmarks projektu | **globální marky `mA`–`mZ`** — `` `A `` skočí i do jiného souboru; přehled `Space sm` |

Globální marky jsou podceňovaný klenot: `mA` na modelu, `mB` na API, `mC` na testu —
a pak se mezi třemi rozdělanými místy přepínáš na dva úhozy, klidně napříč soubory.
Víc v [receptu Marks & jumpy](../recepty/marks-a-jumpy.md).

## Workflow: orientace v cizím repu

```
Space e          → zorientuj se ve struktuře
Space / vzor     → najdi, kde se věc děje
gd / gr          → projdi definice a použití
Ctrl-o Ctrl-o …  → vracej se po vlastní stopě
mA               → důležité místo si označ
```

## Poctivě

- **Multi-root workspace** (VS Code) / **moduly** (JetBrains) přímý ekvivalent nemají —
  nvim je adresářový. V praxi: otevři nadřazený adresář, root detekce se postará.
- Session (`Space qs`) obnoví buffery a okna, ne stav pluginů či terminálů.

## Cvičení
- [ ] Otevři projekt, rozdělej tři soubory a přepínej: `Shift-h/l`, `Space ,`, `Ctrl-^`.
- [ ] Označ dvě místa `mA` / `mB` v různých souborech a skákej `` `A `` / `` `B ``.
- [ ] Prohledej projekt `Space /`, prokliknej výsledek, vrať se `Ctrl-o`.
- [ ] Zavři nvim, spusť znovu, `Space qs` — jsi tam, kde jsi byl.

## Co dál
[B08 — Autocomplete a snippety](B08-autocomplete.md).
