# A06 — Hledání a nahrazování

Cíl: umět v souboru **najít** text a **nahradit** ho — včetně toho, co znáš z IDE jako
„Replace / Skip / Replace All" a „nahradit jen ve výběru".

## Hledání

| Klávesa | Co dělá |
|---------|---------|
| `/vzor` `Enter` | hledej `vzor` směrem dopředu |
| `?vzor` `Enter` | hledej dozadu |
| `n` / `N` | další / předchozí výskyt (ve směru hledání) |
| `*` / `#` | najdi slovo **pod kurzorem** dopředu / dozadu |
| `:noh` | zruš zvýraznění výsledků (když ti svítí celá obrazovka) |

Tip: hledání respektuje `smartcase` (v LazyVim zapnuto) — malými písmeny hledáš
case-insensitive, jakmile napíšeš velké písmeno, hledá přesně.

## Nahrazování — příkaz `:substitute` (`:s`)

Struktura:

```
:[rozsah]s/co/čím/[flagy]
```

### Rozsahy (prefix před `s`) — řeší „jen na některých řádcích"

| Zápis | Kde nahrazuje |
|-------|---------------|
| `:s/…` | jen aktuální řádek |
| `:%s/…` | celý soubor |
| `:10,20s/…` | řádky 10–20 |
| `:.,+5s/…` | od aktuálního (`.`) o 5 řádků dolů |
| `:.,$s/…` | od aktuálního po konec (`$`) |
| `:'<,'>s/…` | **jen ve vizuálním výběru** — označíš `V`, zmáčkneš `:` a vim `'<,'>` předvyplní sám |

### Flagy (za posledním lomítkem)

| Flag | Co dělá |
|------|---------|
| `g` | všechny výskyty na řádku (bez něj se nahradí jen **první**) |
| `c` | **confirm** — u každého výskytu se zeptá (viz níže) |
| `i` / `I` | ignoruj velikost písmen / vynuť rozlišování |

### Confirm (`c`) = tvoje IDE tlačítka

S flagem `c` se vim u každého výskytu zastaví a čeká na klávesu:

| Klávesa | Význam | IDE ekvivalent |
|---------|--------|----------------|
| `y` | nahraď tenhle | **Replace** |
| `n` | přeskoč | **Skip** |
| `a` | nahraď tenhle i všechny další | **Replace All** |
| `q` | skonči | **Close** |
| `l` | nahraď tenhle a skonči | (last) |
| `Ctrl-e` / `Ctrl-y` | odscrolluj dolů / nahoru (rozhlédnout se) | — |

## Nejčastější recept

**Interaktivní find & replace v celém souboru** (přesně to z IDE):
```
:%s/starý/nový/gc
```
**Jen ve výběru** — označ `V` (řádky), pak:
```
:'<,'>s/starý/nový/gc
```

## Regex — vim má vlastní dialekt

vim není PCRE. Nejčastější rozdíly:

| Chceš | Píšeš |
|-------|-------|
| skupina | `\(…\)` (s backslashem!) |
| alternace „a nebo b" | `foo\|bar` |
| „jeden a víc" | `\+` |
| hranice slova | `\<slovo\>` |
| v náhradě: celý match | `&` nebo `\0` |
| v náhradě: 1. skupina | `\1` |
| v náhradě: velká/malá písmena | `\U` `\L` … `\E` |

Příklad — prohodit `jmeno prijmeni` na `prijmeni, jmeno`:
```
:%s/\(\w\+\) \(\w\+\)/\2, \1/
```

## Cvičení

Otevři cvičný soubor:
```bash
nvim ../cviceni/A06-nahrazovani.txt
```

- [ ] Najdi slovo `foo` přes `/foo` a proskákej výskyty `n` / `N`.
- [ ] Nahraď **první** `barva` na řádku za `color` (bez `g`).
- [ ] Nahraď **všechny** `barva` na jednom řádku (`g`).
- [ ] Nahraď v celém souboru `TODO` za `HOTOVO` **s potvrzováním** (`:%s/TODO/HOTOVO/gc`) a vyzkoušej `y`, `n`, `a`.
- [ ] Označ tři řádky přes `V` a nahraď v nich `x` za `-` jen ve výběru.

## Co dál
[Lekce A07 — Undo, opakování a makra](A07-undo-opakovani-makra.md).
