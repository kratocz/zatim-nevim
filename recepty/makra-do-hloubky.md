# Recept — Makra do hloubky

Základy (`qa…q`, `@a`, `@@`) učí [A07](../lekce/A07-undo-opakovani-makra.md). Tady je
zbytek: jak psát makra, která nezradí, jak je opravit bez přenahrávání a jak je pouštět
hromadně.

## Anatomie robustního makra

1. **Začni normalizací pozice** — `0` (začátek řádku) nebo `/vzor` `Enter`, ať makro
   nefunguje jen „odtud, kde zrovna stojím".
2. **Používej text objekty a `f`/`t`** místo počítání (`ciw`, `f,` — ne `3l`), ať přežije
   různě dlouhé řádky.
3. **Skonči připravený na další běh** — typicky `j0` (další řádek) nebo `n` (další nález).
4. **Selhávej čistě** — když `f,` nebo `n` nenajde cíl, makro se zastaví. To je feature:
   `99@a` pak samo skončí na konci dat.

## Makra jsou jen registry ⭐

Makro v `a` je obyčejný text v registru `a`. Z toho plyne:

| Chci | Jak |
|------|-----|
| Podívat se, co makro dělá | `"ap` — vloží ho jako text |
| **Opravit makro bez přenahrávání** | `"ap` → uprav jako text → `0"ay$` (yankni zpět, bez `yy`!) |
| Přidat kroky na konec makra | nahrávej do velkého písmene: `qA … q` |
| Uložit makro natrvalo | je to jen text — klidně do poznámek/configu |

Pozor na `yy` při yanknutí zpět: vzal by i konec řádku (Enter navíc v makru).
Proto `0"ay$`.

## Hromadné spouštění

| Chci | Jak |
|------|-----|
| N-krát | `15@a` |
| Na každém řádku výběru | `:'<,'>normal @a` |
| Na každém řádku se vzorem | `:g/vzor/normal @a` ([B02](../prechod-z-ide/B02-global-command.md)) |
| Do konce dat (necháš doběhnout) | `999@a` — zastaví se na první chybě |

## Rekurzivní makro

Makro, které na konci volá samo sebe — běží, dokud nenarazí na chybu (typicky konec
souboru):

```
qaq        " 1) vyprázdni registr a (důležité!)
qa         " 2) nahrávej…
…kroky…
j0         " 3) posuň se na další řádek
@a         " 4) zavolej sám sebe
q          " 5) konec nahrávání
@a         " 6) spusť — jede až do konce
```

Krok 1 je klíčový: kdyby v `a` zbylo staré makro, spustilo by se už **během nahrávání**.

## Bonus: `@:`

Zopakuje poslední `:` příkaz (třeba `:'<,'>normal @a` na dalším výběru). Šetří psaní.

## Cvičení
Otevři `../cviceni/makra-do-hloubky.txt`:
- [ ] Nahraj makro „obal řádek do uvozovek a přidej čárku" a spusť ho na sekci přes `:'<,'>normal @a`.
- [ ] Totéž rekurzivně: `qaq`, nahraj s `@a` na konci, nech doběhnout.
- [ ] Vlož makro jako text (`"ap`), změň v něm uvozovky na apostrofy, yankni zpět (`0"ay$`) a spusť.
