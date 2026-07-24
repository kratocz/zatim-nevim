# A02 — Tři režimy pořádně

Cíl: pochopit, proč vim „přepíná režimy", a umět mezi nimi plynule přecházet. Tohle je
mentální model, na kterém stojí všechno ostatní — jakmile ho máš, vim přestane překvapovat.

## Proč vůbec režimy

Běžný editor má jeden režim: klávesy = text. Vim odděluje **psaní** od **ovládání**, takže
v Normal módu je celá klávesnice plná příkazů (mazání, pohyb, kopírování) bez nutnosti
mačkat Ctrl. Cena: musíš vědět, ve kterém módu jsi.

## Tři hlavní režimy (+ jeden bonusový)

| Mód | K čemu | Poznáš podle |
|-----|--------|--------------|
| **Normal** | pohyb + příkazy; sem se pořád vracíš přes `Esc` | žádný indikátor / prázdný řádek dole |
| **Insert** | píšeš text jako v každém editoru | `-- INSERT --` dole |
| **Visual** | označuješ text | `-- VISUAL --` dole |
| Command-line | příkazy `:…`, hledání `/…` | kurzor skočí na spodní řádek |

## Vstup do Insert módu — víc než jen `i`

Nejde jen o `i`. Kam se kurzor postaví, si vybíráš:

| Klávesa | Kam tě přepne do psaní |
|---------|------------------------|
| `i` | **před** kurzor (insert) |
| `a` | **za** kurzor (append) |
| `I` | na **začátek** řádku (první nemezera) |
| `A` | na **konec** řádku |
| `o` | otevře **nový řádek pod** a píšeš |
| `O` | otevře **nový řádek nad** a píšeš |

Zpět do Normal módu vždycky **`Esc`** (nebo `Ctrl-[`, což je totéž a blíž prstům).

## Vstup do Visual módu

| Klávesa | Výběr |
|---------|-------|
| `v` | po znacích |
| `V` | po celých řádcích |
| `Ctrl-v` | blokový (sloupcový) výběr |

Když máš něco označeného, můžeš na to pustit operátor: `d` (smaž), `y` (zkopíruj),
`c` (přepiš), `>` (odsaď). O tom je [lekce A04](A04-gramatika.md).

## Cvičení
- [ ] Vyzkoušej všech šest vstupů do Insertu (`i a I A o O`) a sleduj, kam skočí kurzor.
- [ ] Přepni do Visual (`v`), označ pár znaků, `Esc` ven.
- [ ] Zvykni si po každé editaci mačkat `Esc` — návrat do Normal módu je „domovská pozice".

## Co dál
[Lekce A03 — Pohyb](A03-pohyb.md): jak se rychle dostat kamkoli.
