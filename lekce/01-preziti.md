# Lekce 01 — Přežití

Cíl: umět otevřít soubor, něco v něm změnit, uložit a zavřít — a nezaseknout se.
Nic víc zatím neřeš. Tohle je minimum, se kterým přežiješ jakýkoli vim na jakémkoli serveru.

## Napřed: vimtutor
Než začneš, projdi vestavěný tutoriál (30 min, nic neinstaluješ):
```bash
vimtutor
```

## Osm věcí

1. **Pohyb:** `h` `j` `k` `l` = vlevo, dolů, nahoru, vpravo.
   Tip na zapamatování: `j` vypadá jako šipka dolů.
2. **Psaní:** `i` = vstup do Insert módu (teď píšeš normálně).
3. **Zpět do klidu:** `Esc` = zpátky do Normal módu. Když nevíš, kde jsi, zmáčkni `Esc`.
4. **Uložit:** `:w` (napíšeš dvojtečku, `w`, Enter).
5. **Zavřít:** `:q`. Zavřít bez uložení: `:q!`. Uložit a zavřít: `:wq` nebo `ZZ`.
6. **Smazat znak:** `x`.
7. **Smazat řádek:** `dd`.
8. **Vrátit zpět:** `u` (undo). Znovu provést: `Ctrl-r`.

## Cvičení
Otevři cvičný soubor a zkus na něm všech osm věcí:
```bash
nvim ../cviceni/01-preziti.txt
```
(nebo přes svůj alias: `nevim ../cviceni/01-preziti.txt` 😄)

- [ ] Přesuň se po souboru jen pomocí `h j k l` (bez šipek).
- [ ] Vstup do psaní přes `i`, napiš větu, `Esc`.
- [ ] Smaž jeden znak (`x`) a jeden řádek (`dd`).
- [ ] Vrať to zpět přes `u`.
- [ ] Ulož (`:w`) a zavři (`:q`).

## Co dál
Až tohle půjde bez přemýšlení → [lekce 02: gramatika](02-gramatika.md) (zatím TODO).
