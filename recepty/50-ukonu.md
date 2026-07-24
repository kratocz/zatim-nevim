# Recept — 50 nejčastějších úkonů

Velký tahák: „chci udělat X → napíšu Y". Položky označené 🅻 jsou z LazyVim (jinde nemusí
platit); zbytek je čistý vim. Když něčemu nerozumíš, hledej v [Tracku A](../lekce/).

## Řádky

| # | Chci | Úhozy |
|---|------|-------|
| 1 | Smazat řádek | `dd` |
| 2 | Duplikovat řádek | `yyp` (nebo `:t.`) |
| 3 | Přesunout řádek dolů / nahoru | `Alt-j` / `Alt-k` 🅻 |
| 4 | Spojit dva řádky | `J` (s mezerou), `gJ` (bez) |
| 5 | Rozdělit řádek v místě kurzoru | `i` `Enter` `Esc` |
| 6 | Prázdný řádek pod / nad (bez psaní) | `o` `Esc` / `O` `Esc` |
| 7 | Odsadit / zrušit odsazení | `>>` / `<<` |
| 8 | Zarovnat odsazení bloku / souboru | `=ip` / `gg=G` |
| 9 | Zakomentovat řádek / výběr | `gcc` / `gc` 🅻 |

## Slova a znaky

| # | Chci | Úhozy |
|---|------|-------|
| 10 | Přepsat slovo | `ciw` |
| 11 | Smazat slovo (i s mezerou) | `daw` |
| 12 | Přepsat do konce řádku | `C` |
| 13 | Smazat do konce řádku | `D` |
| 14 | Prohodit dva znaky | `xp` |
| 15 | Prohodit dva řádky | `ddp` |
| 16 | Změnit velikost písmen | `~` znak, `gUiw` / `guiw` slovo |
| 17 | Zvýšit / snížit číslo pod kurzorem | `Ctrl-a` / `Ctrl-x` |
| 18 | Nahradit jeden znak | `r{znak}` |

## Uvnitř struktur

| # | Chci | Úhozy |
|---|------|-------|
| 19 | Přepsat obsah závorek | `ci(` |
| 20 | Přepsat obsah uvozovek | `ci"` |
| 21 | Smazat i se závorkami | `da(` |
| 22 | Obalit slovo uvozovkami | `gsaiw"` 🅻 ([surround](surround.md)) |
| 23 | Změnit `"` na `'` | `gsr"'` 🅻 |
| 24 | Rozšiřovat výběr po celcích | `Ctrl-Space`, zúžit `Backspace` 🅻 |
| 25 | Skok na párovou závorku | `%` |

## Schránka

| # | Chci | Úhozy |
|---|------|-------|
| 26 | Vložit (ze systémové schránky) | `p` 🅻 (jinde `"+p`) |
| 27 | Vložit před kurzor / nad řádek | `P` |
| 28 | Vložit poslední **zkopírované** (ne smazané) | `"0p` |
| 29 | Vložit v Insert módu | `Ctrl-r "` (nebo `Ctrl-r 0`) |
| 30 | Zkopírovat celý soubor | `:%y` |

## Hledání a nahrazení

| # | Chci | Úhozy |
|---|------|-------|
| 31 | Najít slovo pod kurzorem | `*` |
| 32 | Zrušit zvýraznění nálezů | `Esc` 🅻 (jinde `:noh`) |
| 33 | Nahradit v souboru s potvrzováním | `:%s/x/y/gc` |
| 34 | Nahradit jen ve výběru | `V`…`:'<,'>s/x/y/g` |
| 35 | Postupně přejmenovat výskyty | `*` → `cgn` → `.` / `n` |

## Soubory a okna

| # | Chci | Úhozy |
|---|------|-------|
| 36 | Rychle otevřít soubor | `Space Space` 🅻 |
| 37 | Přepnout na předchozí soubor (tam-zpět) | `Ctrl-^` |
| 38 | Uložit | `:w` (i `Ctrl-s` 🅻) |
| 39 | Zavřít buffer | `Space bd` 🅻 |
| 40 | Rozdělit okno svisle / vodorovně | `Space \|` / `Space -` 🅻 |
| 41 | Hledat text v projektu | `Space /` 🅻 |

## Pohyb

| # | Chci | Úhozy |
|---|------|-------|
| 42 | Začátek / konec souboru | `gg` / `G` |
| 43 | Na řádek 42 | `42G` nebo `:42` |
| 44 | Konec / začátek řádku | `$` / `0` (první znak `^`) |
| 45 | Doskočit kamkoli na obrazovce | `s` + 2 znaky 🅻 (flash) |
| 46 | Zpátky, kde jsem byl | `Ctrl-o` (vpřed `Ctrl-i`) |
| 47 | Na místo poslední změny | `g;` |

## Meta

| # | Chci | Úhozy |
|---|------|-------|
| 48 | Zopakovat poslední změnu | `.` |
| 49 | Vrátit / znovu provést | `u` / `Ctrl-r` |
| 50 | Spočítat výskyty vzoru | `:%s/vzor//gn` |

---

Vytiskni, pověs, používej. A až ti většina přejde do prstů — už tahák nepotřebuješ,
mluvíš vimsky. 🎓
