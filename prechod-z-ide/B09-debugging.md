# B09 — Debugging

Poctivě na úvod: tohle je oblast, kde IDE drží největší náskok. Ale **nvim-dap**
(Debug Adapter Protocol — stejný protokol, na kterém stojí debugger ve VS Code) po
nastavení zvládne breakpointy, krokování, watch i REPL přímo v editoru.

## Zapnutí

1. `:LazyExtras` → zapni **`dap.core`** (jádro + UI + klávesy).
2. Adaptér pro tvůj jazyk obvykle přinese jazykový Extra (`lang.python`,
   `lang.java` — propojí jdtls s debuggerem, …); chybějící adaptéry doinstaluje Mason.

### ⭐ Máš v repu `.vscode/launch.json`?

nvim-dap ho umí číst a LazyVim ho načítá automaticky. Debug konfigurace z VS Code
se stěhují s tebou — pro přecházejícího člověka obrovská úleva.

## Mapa kláves

| Akce | VS Code | IntelliJ | LazyVim |
|------|---------|----------|---------|
| Breakpoint | `F9` | `Cmd+F8` | `Space db` |
| Podmíněný breakpoint | (pravý klik) | (pravý klik) | `Space dB` |
| Start / Continue | `F5` | `F9` | `Space dc` |
| Step Over | `F10` | `F8` | `Space dO` |
| Step Into | `F11` | `F7` | `Space di` |
| Step Out | `Shift+F11` | `Shift+F8` | `Space do` |
| Run to Cursor | — | `Alt+F9` | `Space dC` |
| Stop | `Shift+F5` | `Cmd+F2` | `Space dt` |
| Debug Console / REPL | — | — | `Space dr` |
| Panely (variables, stacky…) | automaticky | automaticky | `Space du` |
| Hodnota proměnné pod kurzorem | hover myší | hover myší | `Space dw` |

Mnemotechnika: všechno debugové žije pod `Space d` — zmáčkni a which-key ti zbytek ukáže.

## Doporučený žebřík (bez ideologie)

1. **Běžné dluhy** (breakpoint, krokování, kouknout na proměnnou) — dap zvládá dobře.
2. **print/log debugging** není ostuda — v kombinaci s `Ctrl+/` terminálem je to rychlá smyčka.
3. **Těžké seance** (multi-thread, hot-swap, složité evaluace) — otevři IDE. Hybrid
   z [B04](B04-jetbrains.md) platí i tady; nikdo ti nebere právo na dva nástroje.

## Poctivě

- Nastavení adaptérů pro méně obvyklé jazyky/frameworky umí být frustrující — počítej
  s tím a nastavuj ve chvíli klidu, ne uprostřed hašení produkce.
- Vizuální komfort (inline hodnoty u řádků, drag-and-drop stack) je v IDE dál.

## Cvičení
- [ ] Zapni `dap.core` + Extra svého jazyka.
- [ ] V malém skriptu: `Space db` breakpoint, `Space dc` start, `Space dO` pár kroků.
- [ ] Prohlédni si proměnnou přes `Space dw` a panely `Space du`.
- [ ] Pokud máš projekt s `.vscode/launch.json`, ověř, že se konfigurace nabídne.

## Co dál
🎉 **Track B je kompletní.** Pokračuj [Trackem C — Recepty](../recepty/README.md),
nebo zpět na [index Tracku B](README.md).
