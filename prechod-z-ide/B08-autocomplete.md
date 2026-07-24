# B08 — Autocomplete a snippety

IntelliSense v LazyVim = **blink.cmp** (našeptávač) + LSP + snippety. Funguje hned po
instalaci — tahle lekce je o tom, jak ho ovládat a co čekat. Zdroje návrhů: language
server, snippety, cesty k souborům, slova z bufferu.

## Ovládání našeptávače

| Co | Jak |
|----|-----|
| Nabídka | vyskakuje sama při psaní; vynutit: `Ctrl-Space` |
| Pohyb po nabídce | `Ctrl-n` / `Ctrl-p` (nebo šipky) |
| Potvrdit | `Enter` |
| Zavřít nabídku (a psát dál po svém) | `Ctrl-e` |
| Dokumentace k položce | zobrazuje se sama u vybrané položky |
| Snippet: skok po polích | `Tab` / `Shift-Tab` |

Nápověda signatury (parametry funkce) se ukazuje sama při psaní volání.

## Snippety

- **friendly-snippets** (VS Code formát) jsou předinstalované — `for`, `fn`, `if`…
  vyber v nabídce, `Enter`, a `Tab`em skáčeš po vyplňovaných polích.
- Vlastní snippety: stejný JSON formát jako ve VS Code, takže případná sbírka
  se dá přenést.

## Drobnosti, které z IDE čekáš

| V IDE | LazyVim |
|-------|---------|
| Parameter hints / inlay hints | `Space uh` (toggle) |
| Auto-import při doplnění | dělá LSP sám (dle serveru) |
| Doplňování v příkazové řádce | funguje i v `:` (příkazy, cesty) |

## AI doplňování (Copilot & spol.)

`:LazyExtras` → `ai.copilot` (případně `ai.copilot-chat`). Návrhy se pak objevují
přímo mezi položkami našeptávače. Stejnou cestou existují extras i pro další nástroje.

## Poctivě

- **Řazení návrhů** — JetBrains ML ranking a kontextové řazení bývá chytřejší.
  Zdroj dat je ale stejný (language server), takže *co* se nabízí, je srovnatelné;
  liší se hlavně pořadí.
- Framework magie (např. Spring properties napříč soubory) závisí na LSP — IDE
  s vlastním indexem tu umí víc.

## Cvičení
- [ ] V kódu si vynuť nabídku `Ctrl-Space` a projdi ji `Ctrl-n`/`Ctrl-p`.
- [ ] Rozbal snippet (`for`…) a proskákej pole `Tab`em.
- [ ] Zapni/vypni inlay hints `Space uh` a rozhodni se, co ti sedí.
- [ ] Zkus `Ctrl-e` — psát dál bez našeptávače je taky dovednost.

## Co dál
[B09 — Debugging](B09-debugging.md).
