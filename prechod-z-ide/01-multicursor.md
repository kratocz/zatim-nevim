# B1 — Multi-cursor po vimácku

Nejčastější otázka lidí z VS Code: *„kde je `Cmd+D`?"* Odpověď: vim **nemá** multi-cursor
nativně — a většinou ho nepotřebuje, protože má čtyři přístupy, které jsou v součtu silnější.
Klíč je vybrat správný podle situace.

## Rozhodovací tabulka

| Situace | Nástroj |
|---------|---------|
| Stejná změna slova na mnoha výskytech, chci přeskakovat | **`cgn` + `.`** |
| Stejný text na začátek/konec/sloupec více řádků | **visual block `Ctrl-v`** |
| Změna jen na řádcích, které splňují vzor | **`:g/vzor/normal …`** ([lekce B2](02-global-command.md)) |
| Složitá vícekroková opakovaná úprava | **makro** (`qa … q`, `@a`) |

## 1) `cgn` + `.` — postupná náhrada s přeskakováním

Přesně nahrazuje VS Code „select next occurrence" (`Cmd+D`) + úprava:

1. Postav kurzor na slovo a zmáčkni `*` (nastaví hledaný vzor na to slovo).
2. `cgn` — změní **další výskyt** a nechá tě v Insertu. Napiš nové, `Esc`.
3. `.` — zopakuje změnu na dalším výskytu. `n` — přeskočí výskyt beze změny.

Takhle procházíš výskyty a u každého se rozhoduješ `.` (změň) / `n` (nech). Plná kontrola.

## 2) Visual block `Ctrl-v` — sloupcová editace

Nahrazuje „add cursor to line ends / column selection":

| Chci | Postup |
|------|--------|
| Vložit text na **začátek** N řádků | `Ctrl-v` → `j j` (označ řádky) → `I` → napiš → `Esc` |
| Vložit text na **konec** N řádků | `Ctrl-v` → `j j` → `$` → `A` → napiš → `Esc` |
| Přepsat **sloupec** | `Ctrl-v` označ blok → `c` → napiš → `Esc` |
| Smazat sloupec | `Ctrl-v` označ blok → `d` |

Změna se propíše na všechny řádky bloku **až po `Esc`** — nelekni se, že se během psaní
mění jen první řádek.

## 3) `:g/vzor/normal …` — na řádcích se vzorem

Když má změna proběhnout jen tam, kde je nějaký vzor:
```
:g/console\./normal A  // TODO smazat
```
(na každý řádek s `console.` připoj komentář). Víc v [lekci B2](02-global-command.md).

## 4) Makro — když je to složité

Cokoli, co uděláš ručně, nahraješ jako makro a přehraješ na všech výskytech —
viz [lekce 07](../lekce/07-undo-opakovani-makra.md).

## „Ale já fakt chci VS Code multi-cursor"

Existuje plugin **vim-visual-multi** (nebo `mini.operators`), který přinese doslova
multi-kurzory. Klidně si ho přidej — ale nauč se napřed nativní čtyřku, protože `:g` a makra
zvládnou věci, na které multi-cursor nestačí (podmíněné a vícekrokové úpravy).

## Cvičení
Otevři `../cviceni/multicursor.txt`:
- [ ] Přejmenuj všechny `foo` na `bar` přes `*` → `cgn` → `.` / `n`.
- [ ] Přidej `;` na konec pěti řádků přes `Ctrl-v` + `$` + `A`.
- [ ] Zakomentuj tři řádky najednou přes `Ctrl-v` + `I` + `// ` + `Esc`.

## Co dál
[B2 — `:g` global command](02-global-command.md).
