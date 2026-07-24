# Lekce 00 — Nouzové přežití

Tahle lekce je pro člověka, který právě spustil vim a **neví, jak z něj ven**. Nic víc
zatím neumíš a to je úplně v pořádku. Cíl: spustit, nezpanikařit, a hlavně bezpečně odejít.

## Jak vim vůbec spustit

```bash
vim soubor.txt      # klasický vim
nvim soubor.txt     # neovim (modernější, doporučeno)
```

Když napíšeš jen `vim` bez souboru, otevře se uvítací obrazovka — nevadí.

## Proč to „píše divně"

Zmáčkneš písmena a vim dělá kraviny místo psaní? To proto, že vim startuje v **Normal
módu**, kde klávesy nejsou text, ale **příkazy**. To je celé kouzlo vim a probereme ho
v [lekci 02](02-tri-rezimy.md). Zatím stačí vědět, že existuje záchranná klávesa:

> **`Esc`** = „vrať mě do klidu" (do Normal módu). Když nevíš, kde jsi, zmáčkni `Esc`.

## Jak vim ukončit (to hlavní!)

Nejdřív `Esc` (pro jistotu), pak jeden z těchto příkazů + `Enter`:

| Příkaz | Co udělá |
|--------|----------|
| `:q` | zavři (jen když nejsou neuložené změny) |
| `:q!` | zavři a **zahoď** změny (tvoje záchrana z čehokoli) |
| `:wq` | ulož a zavři |
| `:x` | ulož (jen když je co) a zavři |
| `ZZ` | ulož a zavři (bez dvojtečky, velká Z Z) |
| `ZQ` | zahoď a zavři (bez dvojtečky) |

**Univerzální únik z jakéhokoli stavu:** `Esc` `Esc` `:q!` `Enter`. Tímhle se dostaneš
ven odkudkoli, i když nevíš, co se děje.

## Cvičení
- [ ] Spusť `nvim pokus.txt`.
- [ ] Zmáčkni `Esc`, pak `:q!` a `Enter` — jsi venku. Gratuluju, tohle je nadpoloviční většina lidí. 😄
- [ ] Spusť znovu, zmáčkni `i`, napiš „ahoj", `Esc`, pak `:wq`. Soubor je uložený.

## Co dál
[Lekce 01 — Přežití](01-preziti.md): osm základních věcí, se kterými něco vyeditáš.
