# B5 — Refaktoring

V IDE je refaktoring menu plné kouzel (Rename, Extract, Inline, Change Signature…).
Ve vim světě stojí na dvou nohách: **sémantické** operace přes LSP (záleží na language
serveru) a **textové** operace přes vim gramatiku (fungují vždy a všude). IDE má jen tu
první — a právě ta druhá je důvod, proč vimáci refaktorují rychle i tam, kde LSP nestačí.

## Žebřík refaktoringu

Odshora dolů — začni nejsémantičtějším nástrojem, spadni níž, jen když chybí:

1. **LSP rename / code action** — chápe kód, přejmenuje napříč projektem.
2. **Projektový textový find&replace** — `Space sr` (grug-far) nebo quickfix + `:cfdo`.
3. **`:%s` v souboru** s hranicemi slova (`\<…\>`) — [lekce 06](../lekce/06-hledani-a-nahrazovani.md).
4. **`cgn` + `.`** — interaktivní bodové přejmenování — [B1](01-multicursor.md).

## Sémantická vrstva (LSP)

| Akce v IDE | LazyVim |
|-----------|---------|
| Rename (Shift+F6 / F2) | `Space cr` — bezpečné, napříč projektem |
| Quick Fix / Intention (Alt+Enter, Cmd+.) | `Space ca` (code action) |
| Extract Variable / Method | označ výraz ve Visualu → `Space ca` → „Extract…" |
| Inline | `Space ca` (kde to server nabízí) |
| Organize Imports | `Space cA` (source actions); TS extra přidává `Space co` |
| Reformat | `Space cf` |
| Rename File (+ oprava importů) | `Space cR` (kde server podporuje) |
| Safe Delete | neexistuje — **před smazáním `gr`** (zkontroluj reference) |
| Change Signature | většinou chybí (viz „poctivě" níže) |

**Klíčové:** nabídka `Space ca` je **kontextová** — stoupni kurzorem (nebo výběrem) na
výraz/funkci a koukni, co server nabízí. Extract u TypeScriptu, rust-analyzeru nebo
jdtls (Java: extract method/variable/constant) umí hodně; jinde míň. Prostě to zkus.

## Textová vrstva (vim gramatika)

Tohle v IDE nemáš a je to půlka síly:

- **`cgn` + `.`** — přejmenuj výskyty postupně s rozhodováním u každého.
- **`:g/vzor/normal …`** — strukturální dávková změna ([B2](02-global-command.md)).
- **Makro** — vícekroková přestavba nahraná jednou, přehraná stokrát ([lekce 07](../lekce/07-undo-opakovani-makra.md)).
- **`Ctrl-Space`** (Treesitter extend selection) — přesně uchop uzel (výraz → příkaz →
  blok → funkce) a pak na něj pusť operátor.

## Recept: projektový textový refactor přes quickfix

Když LSP rename nejde (řetězce, komentáře, configy, jazyk bez serveru):

```
Space /  →  najdi vzor (live grep)
Ctrl-q   →  pošli výsledky do quickfix listu
:cfdo %s/\<stare\>/nove/gc | update
```

`cfdo` projede každý soubor z quickfixu, `c` flag se ptá u každého výskytu (tvoje
Replace/Skip/All tlačítka z [lekce 06](../lekce/06-hledani-a-nahrazovani.md)), `update`
uloží změněné. Bez `c` je to tichý „Replace All" napříč projektem.

## Po refaktoringu: úklid diagnostiky

`]d` / `[d` skáče po chybách, `Space xx` (Trouble) dá přehled všech problémů v projektu —
ekvivalent Problems panelu. Projeď, oprav, hotovo.

## Poctivě

- **Change Signature, Move class/package, Extract Interface** — tady JetBrains se svým
  sémantickým indexem vede a LSP standard ekvivalent nemá. Pro Javu/Kotlin s těžkou
  přestavbou platí hybrid z [B4](04-jetbrains.md): udělej to v IDEA (klidně s IdeaVim).
- Kvalita `Space ca` = kvalita language serveru. TypeScript/Rust rozmazlují, jinde střídmě.

## Cvičení
- [ ] Na reálném projektu: přejmenuj symbol přes `Space cr` a zkontroluj `gr`, že se chytlo vše.
- [ ] Označ výraz (`Ctrl-Space`) a projdi nabídku `Space ca` — co tvůj server umí?
- [ ] Zkus quickfix recept: `Space /` → `Ctrl-q` → `:cfdo %s/…/…/gc | update`.
- [ ] Před smazáním funkce si zvykni na reflex `gr`.

## Co dál
[B6 — Git jako GitLens](06-git.md).
