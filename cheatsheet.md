# Cheatsheet — gramatika vim

Vim je **jazyk**: skládáš věty `operátor + pohyb` (nebo `operátor + text objekt`).
Naučíš se pár operátorů a pár pohybů → dostaneš desítky kombinací zdarma.

## Módy
| Mód | K čemu | Jak do něj |
|-----|--------|-----------|
| Normal | pohyb + příkazy (sem se pořád vracíš) | `Esc` |
| Insert | píšeš text | `i` `a` `o` `I` `A` `O` |
| Visual | výběr | `v` (znaky) `V` (řádky) `Ctrl-v` (blok) |
| Command | příkazy `:…` | `:` |

## Pohyby
| Klávesa | Kam |
|---------|-----|
| `h` `j` `k` `l` | vlevo / dolů / nahoru / vpravo |
| `w` `b` `e` | další slovo / předchozí / konec slova |
| `0` `^` `$` | začátek řádku / první znak / konec řádku |
| `gg` `G` | začátek / konec souboru |
| `f{znak}` `t{znak}` | skok na znak / těsně před znak |
| `{` `}` | o odstavec zpět / vpřed |
| `Ctrl-u` `Ctrl-d` | o půl obrazovky nahoru / dolů |

## Operátory (skládají se s pohybem)
| Operátor | Význam | Příklad |
|----------|--------|---------|
| `d` | delete (smaž) | `dw`, `d$`, `dd` (celý řádek) |
| `c` | change (přepiš — smaže + Insert) | `ciw`, `ci(`, `cc` |
| `y` | yank (kopíruj) | `yiw`, `yy` (celý řádek) |
| `>` `<` | odsadit / zrušit odsazení | `>ip` |

## Text objekty (co ovlivnit)
| Objekt | Co | Příklad |
|--------|-----|---------|
| `iw` / `aw` | slovo / slovo + mezera | `diw` |
| `i(` `i)` `ib` | uvnitř kulatých závorek | `ci(` |
| `i{` `i}` `iB` | uvnitř složených závorek | `di{` |
| `i"` `i'` | uvnitř uvozovek | `ci"` |
| `it` | uvnitř HTML/XML tagu | `cit` |
| `ip` / `ap` | odstavec | `yip` |

Mnemotechnika: `i` = *inside* (uvnitř), `a` = *around* (včetně okraje).

## Nezbytné jednotlivosti
| Klávesa | Co |
|---------|-----|
| `u` / `Ctrl-r` | undo / redo |
| `.` | zopakuj poslední změnu |
| `x` / `r{znak}` | smaž znak / nahraď znak |
| `p` / `P` | vlož za / před |
| `o` / `O` | nový řádek pod / nad + Insert |
| `/vzor` `n` `N` | hledej / další / předchozí výskyt |
| `:%s/staré/nové/g` | nahraď v celém souboru |

## LazyVim navrch
| Klávesa | Co |
|---------|-----|
| `Space` | leader → vyskočí which-key nabídka |
| `Space Space` | fuzzy hledání souborů (Telescope) |
| `Space e` | file tree |
| `gd` / `gr` | skok na definici / reference |
| `K` | dokumentace pod kurzorem |
