# Lekce 05 — Kopírování, vkládání a registry

Cíl: pochopit, kam vim odkládá text, který smažeš nebo zkopíruješ — a jak ho vložit,
včetně systémové schránky (clipboard) sdílené s ostatními aplikacemi.

## Yank, delete, put

Ve vim se nekopíruje „do clipboardu", ale do **registru**. Zkopírování je `y` (yank),
mazání `d`/`x` (taky naplní registr), vkládání `p`/`P`.

| Klávesa | Co |
|---------|-----|
| `yy` | zkopíruj řádek |
| `yiw` | zkopíruj slovo |
| `dd` | smaž řádek (a ulož ho do registru) |
| `p` | vlož **za** kurzor / **pod** řádek |
| `P` | vlož **před** kurzor / **nad** řádek |

Protože `d` taky plní registr, „přesunout řádek" = `dd` (vyjmi) → popojdi → `p` (vlož).

## Registry — pojmenované schránky

Registr vybereš prefixem `"` + písmeno. Máš tak víc nezávislých schránek:

| Zápis | Co dělá |
|-------|---------|
| `"ayy` | zkopíruj řádek do registru `a` |
| `"ap` | vlož z registru `a` |
| `"0p` | vlož z **yank registru** — to, cos naposled `y`-nul (nepřepíše ho mazání) |

Proč `"0`: běžné `p` bere z „posledního", takže když něco zkopíruješ a pak smažeš,
`p` vloží to smazané. `"0p` vždycky vloží to, cos **zkopíroval**.

## Systémová schránka (clipboard)

Sdílení s prohlížečem a ostatními appkami jde přes registr `+`:

| Zápis | Co |
|-------|-----|
| `"+y` | zkopíruj do systémové schránky (např. `"+yy` celý řádek) |
| `"+p` | vlož ze systémové schránky |

Tip: v LazyVim bývá tohle často nastavené i na `Space y` / `Space p`. Když `"+y` nefunguje,
tvůj vim nemá clipboard podporu (`nvim` ji obvykle má; ověříš přes `:echo has('clipboard')`).

## Visual mód + vložení

Označíš text ve Visual módu a `p` ho **přepíše** obsahem registru. Pozor: klasické `p`
si přitom vymění registr za přepsaný text; novější neovim má na to `P`, které registr
zachová — takže ve Visualu si zvykni na **`P`**.

## Cvičení
Otevři `../cviceni/05-registry.txt`:
- [ ] Přesuň řádek přes `dd` + `p`.
- [ ] Duplikuj řádek přes `yy` + `p`.
- [ ] Zkopíruj slovo do registru `a` (`"ayiw`) a vlož ho jinam (`"ap`).
- [ ] Zkopíruj řádek do systémové schránky (`"+yy`) a vlož ho mimo vim (třeba do prohlížeče).

## Co dál
[Lekce 06 — Hledání a nahrazování](06-hledani-a-nahrazovani.md).
