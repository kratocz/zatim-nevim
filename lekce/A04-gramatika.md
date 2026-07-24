# A04 — Editační gramatika (srdce vim)

Tohle je nejdůležitější lekce celého kurzu. Když ti cvakne, vim se z „hromady zkratek"
promění v **jazyk**, ve kterém si příkazy skládáš sám, aniž by ses je učil nazpaměť.

## Věta = operátor + pohyb

Editace ve vim je věta:

```
operátor  +  pohyb (nebo text objekt)
```

Např. `d` (delete) + `w` (word) = **`dw`** = smaž slovo. Naučíš se pár operátorů a pár
pohybů → dostaneš desítky kombinací zdarma, protože se **násobí**, nesčítají.

## Operátory

| Operátor | Význam |
|----------|--------|
| `d` | delete — smaž |
| `c` | change — smaž a přepni do Insertu (přepiš) |
| `y` | yank — zkopíruj |
| `>` `<` | odsaď / zruš odsazení |
| `=` | zarovnej odsazení (auto-indent) |

## Text objekty — „na čem" operovat

Pohyby říkají „kam", text objekty říkají „co jako celek". Píšou se `i` (inside — uvnitř)
nebo `a` (around — včetně okraje) + druh:

| Objekt | Co |
|--------|-----|
| `iw` / `aw` | slovo / slovo i s mezerou |
| `i(` `i)` `ib` | uvnitř kulatých závorek |
| `i{` `i}` `iB` | uvnitř složených závorek |
| `i[` `i]` | uvnitř hranatých závorek |
| `i"` `i'` `` i` `` | uvnitř uvozovek |
| `it` / `at` | uvnitř / včetně HTML-XML tagu |
| `ip` / `ap` | odstavec |

## Skládání v praxi

| Napíšeš | Výsledek |
|---------|----------|
| `ciw` | přepiš slovo pod kurzorem |
| `di(` | smaž vše uvnitř závorek |
| `yi"` | zkopíruj text uvnitř uvozovek |
| `dt,` | smaž až (těsně před) čárku |
| `d2w` | smaž dvě slova |
| `>ip` | odsaď celý odstavec |
| `ci{` | přepiš tělo bloku `{ … }` |

Kurzor nemusí být na začátku — `ci(` funguje, i když stojíš kdekoli uvnitř závorek.
To je na text objektech to silné.

## Zdvojení = celý řádek

Když operátor napíšeš dvakrát, působí na **celý řádek**:

- `dd` = smaž řádek
- `yy` = zkopíruj řádek
- `cc` = přepiš řádek (smaže obsah, nechá odsazení, Insert)
- `>>` = odsaď řádek

## Tečka `.` — opakuj poslední změnu

`.` zopakuje tvou poslední editační změnu. Smažeš slovo přes `dw`, popojdeš, `.` smaže
další. Tohle je jeden z nejsilnějších návyků ve vim — probereme ho víc v [lekci A07](A07-undo-opakovani-makra.md).

## Cvičení
Otevři `../cviceni/A04-gramatika.txt`:
- [ ] Přepiš slovo přes `ciw`, obsah závorek přes `ci(`, řetězec přes `ci"`.
- [ ] Smaž až po znak přes `dt.` a `df.` (vnímej rozdíl `t` vs `f`).
- [ ] Odsaď odstavec přes `>ip`.
- [ ] Zopakuj poslední změnu jinde přes `.`.

## Co dál
[Lekce A05 — Kopírování a registry](A05-kopirovani-registry.md): kam se poděje to, co smažeš a zkopíruješ.
