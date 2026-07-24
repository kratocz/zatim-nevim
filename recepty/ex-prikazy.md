# Recept — Ex příkazy a rozsahy: vim jako dávkový editor

Příkazová řádka `:` není jen na ukládání. S **rozsahem** před příkazem edituje celé bloky
najednou — a přes `!` protáhne text jakýmkoli unixovým filtrem. Tohle je vrstva, kterou
GUI editory nemají vůbec.

## Rozsahy (opakování z [A06](../lekce/A06-hledani-a-nahrazovani.md), platí všude)

| Zápis | Rozsah |
|-------|--------|
| `:5,10` | řádky 5–10 |
| `:%` | celý soubor |
| `:.,$` | od kurzoru do konce |
| `:.,+3` | aktuální + 3 dolů |
| `:'<,'>` | vizuální výběr (předvyplní se samo) |

## Přesuny a kopie: `:m` a `:t`

| Chci | Příkaz |
|------|--------|
| Duplikovat řádek | `:t.` |
| Zkopírovat řádek na konec souboru | `:t$` |
| Přesunout řádek na začátek / konec | `:m0` / `:m$` |
| Přesunout blok 5–10 za řádek 20 | `:5,10m20` |
| Přesunout výběr na začátek | `:'<,'>m0` |

## Řazení: `:sort`

| Chci | Příkaz |
|------|--------|
| Seřadit výběr | `:'<,'>sort` |
| Seřadit a **odstranit duplicity** | `:'<,'>sort u` |
| Pozpátku / číselně | `:sort!` / `:sort n` |

## `:normal` — normal-mode klávesy na každý řádek rozsahu

```
:'<,'>normal A;      " přidej ; na konec každého vybraného řádku
:'<,'>normal @a      " spusť makro a na každém vybraném řádku
```

V kombinaci se vzorem je to [B02 — `:g`](../prechod-z-ide/B02-global-command.md).

## `!` — protáhni text externím příkazem ⭐

Rozsah se pošle na stdin programu a **nahradí se jeho výstupem**:

| Chci | Příkaz |
|------|--------|
| Zarovnat sloupce | `:'<,'>!column -t` |
| Seřadit externím sortem | `:%!sort -u` |
| Zformátovat JSON | `:%!jq .` (máš-li jq) |
| Očíslovat řádky | `:'<,'>!cat -n` |

Cokoli, co umí shell, je rázem funkce editoru.

## Vkládání zvenku: `:r`

| Chci | Příkaz |
|------|--------|
| Vložit obsah souboru pod kurzor | `:r cesta/soubor` |
| Vložit výstup příkazu | `:r !date`, `:r !ls` |

## Cvičení
Otevři `../cviceni/ex-prikazy.txt`:
- [ ] Seřaď ovoce a odstraň duplicity (`:'<,'>sort u`).
- [ ] Zarovnej tabulku přes `:'<,'>!column -t`.
- [ ] Zduplikuj řádek `:t.` a přesuň jiný na konec sekce `:m…`.
- [ ] Přidej `;` na konec vybraných řádků přes `:'<,'>normal A;`.
