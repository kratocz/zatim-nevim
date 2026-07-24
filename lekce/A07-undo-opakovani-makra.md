# A07 — Undo, opakování a makra

Cíl: nedělat stejnou práci dvakrát. vim má tři úrovně „udělej to znovu": vrácení, tečku
a makra — od nejjednoduššího po malé automaty.

## Undo / redo

| Klávesa | Co |
|---------|-----|
| `u` | vrať poslední změnu (undo) |
| `Ctrl-r` | znovu proveď (redo) |
| `U` | vrať všechny změny na jednom řádku |

Bonus: neovim umí **undo strom** (větve historie) a persistentní undo (přežije zavření
souboru) — v LazyVim bývá zapnuté.

## Tečka `.` — nejlevnější opakování

`.` zopakuje poslední **editační změnu**. Kombo s pohybem je mocné:

- `cw nový Esc` → popojdi na další slovo `w` → `.` (přepíše ho stejně)
- `A;Esc` (přidej středník na konec) → `j` → `.` (na dalším řádku taky)

Zvyk „udělej změnu tak, aby šla zopakovat tečkou" je jeden z největších skoků v efektivitě.

## Makra — nahraj a přehraj sekvenci

Když `.` nestačí (víc kroků), nahraješ **makro**:

1. `q` + písmeno registru (např. `qa`) — začne nahrávat do `a`.
2. Uděláš posloupnost úhozů (klidně pohyb + editace).
3. `q` — konec nahrávání.
4. `@a` — přehraj makro. `@@` — přehraj poslední makro znovu.
5. `5@a` — přehraj pětkrát. `100@a` — na zbytek souboru (skončí, až narazí na chybu).

**Recept:** makro dělej tak, aby končilo připravené na další řádek (např. začni `0`,
skonči `j`). Pak `@a` opakovaně nebo `99@a` projede celý soubor.

## Multi-cursor po vimácku: `cgn`

vim nemá multi-cursor jako VS Code, ale má lepší trik:

1. Najdi vzor: `*` nad slovem (nebo `/vzor`).
2. `cgn` — změní **další výskyt** a nechá tě v Insertu; napiš nové, `Esc`.
3. `.` — zopakuje změnu na dalším výskytu. `n` — přeskočí výskyt.

Takhle procházíš výskyty a u každého se rozhoduješ `.` (změň) / `n` (přeskoč) — obdoba
interaktivní náhrady, ale s plnou silou editace.

## Cvičení
Otevři `../cviceni/A07-makra.txt`:
- [ ] Přidej středník na konec deseti řádků: `A;Esc`, pak `j.` `j.` … nebo makro `qa A;Esc j q` a `9@a`.
- [ ] Přejmenuj všechny výskyty `foo` přes `*` → `cgn bar Esc` → `.` / `n`.

## Co dál
[Lekce A08 — Více souborů](A08-vice-souboru.md).
