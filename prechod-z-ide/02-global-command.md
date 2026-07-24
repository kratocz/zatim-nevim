# B2 — `:g` global command

Málo známá, ale jedna z nejmocnějších věcí ve vim: *„udělej příkaz na každém řádku, který
(ne)obsahuje vzor."* Nahrazuje spoustu ruční práce i pluginů — a v IDE pro to často není
ani ekvivalent.

## Struktura

```
:[rozsah]g/vzor/příkaz
```

- Výchozí rozsah je **celý soubor** (nemusíš psát `%`).
- `vzor` je regex (vimácký — viz [lekce 06](../lekce/06-hledani-a-nahrazovani.md)).
- `příkaz` je libovolný ex příkaz, který se spustí na každém odpovídajícím řádku.

Opak — řádky, kde vzor **není**:
```
:g!/vzor/příkaz      " nebo kratší:
:v/vzor/příkaz
```

## Nejčastější recepty

| Chci | Příkaz |
|------|--------|
| Smazat všechny řádky se vzorem | `:g/vzor/d` |
| Smazat řádky **bez** vzoru (nech jen matchující) | `:v/vzor/d` |
| Smazat prázdné řádky | `:g/^$/d` |
| Nahradit jen na řádcích se vzorem | `:g/vzor/s/a/b/g` |
| Přesunout matchující řádky na **konec** | `:g/vzor/m$` |
| Zkopírovat matchující řádky na konec | `:g/vzor/t$` |
| Přesunout matchující řádky na **začátek** (obrátí pořadí) | `:g/vzor/m0` |

> Pozor na pořadí: `m$` a `t$` zachovají pořadí řádků, `m0` je obrátí (každý řádek se
> postupně předsune před předchozí).

## Kombo s `normal` = neomezená síla

`:g/vzor/normal {úhozy}` spustí na každém matchi libovolnou **normal-mode** sekvenci —
jako bys tam ručně naťukal klávesy:

```
:g/^/normal A;                 " přidej ; na konec KAŽDÉHO řádku
:g/TODO/normal I// x           " před každý TODO řádek dej '// x'
:g/error/normal @a             " spusť makro @a na každém řádku s 'error'
```

Tohle je ta pravá „multi-cursor" síla vim: podmínka (`vzor`) + akce (`normal …`) přes celý
soubor jedním příkazem.

## Praktické příklady

```vim
:g/TODO/m$          " posbírej všechny TODO na konec souboru
:g/^\s*$/d          " smaž řádky obsahující jen bílé znaky
:g/^#/t.            " zduplikuj každý řádek začínající #
:v/^\d/d            " nech jen řádky začínající číslicí
```

## Cvičení
Otevři `../cviceni/global-command.txt`:
- [ ] Smaž všechny prázdné řádky: `:g/^$/d`.
- [ ] Posbírej všechny řádky s `TODO` na konec: `:g/TODO/m$`.
- [ ] Přidej `;` na konec každého neprázdného řádku: `:g/./normal A;`.
- [ ] Nech jen řádky obsahující `keep`: `:v/keep/d`.

## Co dál
[B3 — Z VS Code do vim](03-vscode.md), nebo zpět na [index Tracku B](README.md).
