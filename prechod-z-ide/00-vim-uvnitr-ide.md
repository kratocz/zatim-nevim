# B0 — vim *uvnitř* tvého IDE

Nejsmířlivější způsob, jak začít: **nemusíš nikam utíkat.** Zapneš si vim ovládání přímo
ve VS Code nebo v JetBrains a učíš se gramatiku v prostředí, které už znáš — s debuggerem,
refaktoringem a vším pohodlím IDE po ruce. Editaci děláš vimácky, zbytek beze změny.

## Proč začít právě takhle

- **Nízká bariéra** — neřešíš instalaci a konfiguraci celého neovim naráz.
- **Učíš to důležité** — 90 % zisku z vim je editační gramatika (Track A, lekce 02–07),
  a ta funguje i v emulaci uvnitř IDE.
- **Nic neztrácíš** — IDE zkratky, které máš rád, zůstávají; vim je jen navrch.

## VS Code

Dvě možnosti:

| Rozšíření | Co to je | Pro koho |
|-----------|----------|----------|
| **VSCodeVim** | emulace vim v JavaScriptu | většina lidí — snadné, stačí nainstalovat |
| **vscode-neovim** | skutečný neovim jako backend | pokročilí — chtějí opravdové vim chování a pluginy |

Začni **VSCodeVim** (Extensions → hledej „Vim" → Install). Konfiguruje se v `settings.json`.
Osvědčené drobnosti:

```jsonc
{
  "vim.insertModeKeyBindings": [
    { "before": ["j", "k"], "after": ["<Esc>"] }  // 'jk' = Esc, bez sahání do rohu
  ],
  "vim.useSystemClipboard": true,                  // y/p sdílí schránku s VS Code
  "vim.hlsearch": true,
  "editor.lineNumbers": "relative"                 // pohyby 5j / 3k rovnou vidíš
}
```

## JetBrains (IntelliJ, PyCharm, WebStorm, Rider…)

Oficiální plugin **IdeaVim** (od JetBrains): Settings → Plugins → hledej „IdeaVim" → Install
→ restart. Konfiguruje se v souboru `~/.ideavimrc` (syntaxe jako klasický `.vimrc`):

```vim
inoremap jk <Esc>
set clipboard+=unnamed      " sdílená schránka
set relativenumber
set which-key               " nápověda kláves (plugin)
```

IdeaVim navíc umí volat akce IDE z vim světa přes `:action`, takže si můžeš namapovat
třeba refaktoring na leader klávesu.

## Co funguje a co ne

- ✅ **Funguje:** módy, operátory, pohyby, text objekty, visual, `.`, registry, makra,
  `:s`, `:g` — celá gramatika, kterou tě učí Track A.
- ⚠️ **Nefunguje / jinak:** nativní neovim pluginy (LSP máš z IDE, ne z vim), některé
  okrajové příkazy. Emulace pokrývá 95 % denní práce.

## Doporučené rozdělení práce

Nech si **IDE zkratky** na to, v čem je IDE lepší (debugger, vizuální refaktoring, git UI),
a **vim** na samotnou editaci textu. Nemusíš být purista — hybrid je legitimní a produktivní.

## Cvičení
- [ ] Nainstaluj VSCodeVim nebo IdeaVim a namapuj si `jk` na `Esc`.
- [ ] Zapni `relativenumber` a zkus pohyby `5j`, `3k`.
- [ ] Projdi si na reálném souboru gramatiku z [lekce 04](../lekce/04-gramatika.md) — `ciw`, `di(`, `>ip` — rovnou v IDE.

## Co dál
[B1 — Multi-cursor po vimácku](01-multicursor.md): jak nahradit `Cmd+D`.
