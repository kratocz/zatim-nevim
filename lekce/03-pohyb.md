# Lekce 03 — Pohyb

Cíl: dostat kurzor kamkoli bez šipek a bez myši. Rychlý pohyb je základ, protože většina
příkazů vim = „udělej něco **tam, kam se posuneš**".

## Po řádku

| Klávesa | Kam |
|---------|-----|
| `h` `l` | znak vlevo / vpravo |
| `0` | úplný začátek řádku |
| `^` | první nemezera na řádku |
| `$` | konec řádku |
| `w` / `W` | začátek dalšího slova (`W` ignoruje interpunkci) |
| `b` / `B` | začátek předchozího slova |
| `e` / `E` | konec slova |
| `f{znak}` | skoč **na** další výskyt znaku na řádku |
| `t{znak}` | skoč **těsně před** další výskyt znaku |
| `;` / `,` | zopakuj poslední `f`/`t` vpřed / vzad |

## Po souboru

| Klávesa | Kam |
|---------|-----|
| `j` `k` | řádek dolů / nahoru |
| `gg` | první řádek souboru |
| `G` | poslední řádek souboru |
| `{číslo}G` nebo `:{číslo}` | na konkrétní řádek (např. `42G` nebo `:42`) |
| `{` / `}` | o odstavec zpět / vpřed |
| `Ctrl-d` / `Ctrl-u` | o půl obrazovky dolů / nahoru |
| `Ctrl-f` / `Ctrl-b` | o celou obrazovku vpřed / vzad |
| `H` `M` `L` | na horní / prostřední / dolní řádek obrazovky |

## Počty (count) — násobení pohybu

Před většinu pohybů můžeš napsat číslo: `3w` = o tři slova vpřed, `5j` = o pět řádků dolů,
`2f,` = na druhou čárku. Tenhle princip „count + příkaz" se ti bude hodit všude.

## Skoky zpátky

| Klávesa | Co |
|---------|-----|
| `Ctrl-o` | skoč zpět na předchozí pozici (jako „back" v prohlížeči) |
| `Ctrl-i` | skoč vpřed |
| `` `` `` | zpět na místo před posledním skokem |

## Cvičení
Otevři `../cviceni/03-pohyb.txt` a bez šipek:
- [ ] Dostaň se na řádek 10 přes `:10` i přes `10G`.
- [ ] Skákej po slovech přes `w` a `b`, po znacích přes `f` a `t`.
- [ ] Zkus `3w`, `2f-`, `$` a `^`.

## Co dál
[Lekce 04 — Editační gramatika](04-gramatika.md): tady se to celé spojí v jazyk.
