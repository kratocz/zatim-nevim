# B06 — Git jako GitLens

V IDE máš Source Control panel, gutter značky změn a GitLens blame. LazyVim to skládá ze
dvou vrstev: **gitsigns** (v bufferu — značky a práce s hunky, jako gutter v IDE) a
**lazygit** (plné UI v terminálu — jako Source Control panel na steroidech). K tomu pár
pickerů. Výsledek: z editoru nemusíš kvůli gitu vůbec odcházet.

## Mapa: co znáš z IDE → LazyVim

| V IDE / GitLens | LazyVim |
|-----------------|---------|
| Source Control panel (stage, commit, push) | `Space gg` — lazygit |
| Značky změn v gutteru | gitsigns — automaticky (▎ u změněných řádků) |
| Další / předchozí změna v souboru | `]h` / `[h` |
| Stage hunk z gutteru | `Space ghs` (stage), zpět `Space ghu` |
| Revert/discard hunk | `Space ghr` (reset hunk) |
| Náhled změny (co je v hunku) | `Space ghp` (preview) |
| Inline blame řádku (GitLens) | `Space gb`, podrobně `Space ghb` |
| Otevřít na GitHubu (GitLens Open on Remote) | `Space gB` |
| Diff souboru proti HEAD | `Space ghd` |
| Historie commitů | `Space gc` (picker), plná historie v lazygitu |
| Git status → skoč na změněný soubor | `Space gs` |

## lazygit za 60 sekund

`Space gg` otevře lazygit. Panely přepínáš čísly/šipkami (`h`/`l`), v panelu se hýbeš
`j`/`k`, `Enter` = ponořit se (soubor → hunky → řádky), `Esc` = zpět, **`?` = nápověda
všech kláves** (nejdůležitější klávesa).

| Klávesa (v panelu Files) | Co |
|--------------------------|-----|
| `Space` | stage / unstage souboru (uvnitř souboru: stage hunk/řádků) |
| `a` | stage / unstage všeho |
| `c` | commit (zpráva se píše rovnou tam) |
| `A` | amend posledního commitu |
| `P` / `p` | push / pull |
| `s` | stash |
| `q` | zavřít a zpět do editoru |

V panelu Branches: `Space` = checkout, `n` = nová větev. Víc netřeba — `?` tě podrží.

## Typický workflow (celý bez opuštění editoru)

```
edituješ …
]h              → skoč na svou změnu
Space ghp       → mrkni, co přesně je v hunku
Space ghs       → stage jen tenhle hunk (zbytek souboru necháš)
Space gg  c  P  → lazygit: commit, push
```

Tohle je ekvivalent „partial stage" klikání v IDE — jen rychlejší, protože hunky
stageuješ přímo tam, kde edituješ.

## Poctivě

- **GitLens má bohatší historii** — line history, heatmapy, porovnávání libovolných
  revizí v pěkném UI. lazygit + `Space gc` pokryjí 90 % běžné práce; na zbytek existují
  pluginy (diffview.nvim), ale nejsou v LazyVim defaultu.
- **Merge konflikty** řeší lazygit slušně (vybíráš strany), ale vizuální 3-way merge
  z IDE je pohodlnější. Pro těžké konflikty klidně otevři IDE — hybrid platí i tady.

## Cvičení
V libovolném repu (klidně v tomhle):
- [ ] Změň soubor, `]h` na hunk, `Space ghp` náhled, `Space ghs` stage, `Space ghu` vrať stage zpět.
- [ ] `Space gb` na řádku, který jsi nepsal ty — kdo a kdy ho změnil?
- [ ] `Space gg` → projdi panely, `?` na nápovědu, `q` ven. (Nic nemusíš commitovat.)
- [ ] `Space gB` — otevři aktuální soubor na GitHubu.

## Co dál
[B07 — Multi-file & workspace](B07-workspace.md).
