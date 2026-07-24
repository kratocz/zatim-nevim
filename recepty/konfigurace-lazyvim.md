# Recept — Konfigurace LazyVim: option, keymapa, plugin

LazyVim není „hotový produkt, nesahat" — je to distribuce, do které se vrství vlastní
config. Všechno tvoje žije v `~/.config/nvim/` a přežije aktualizace.

## Kde co je

```
~/.config/nvim/
├── lua/config/
│   ├── options.lua    ← nastavení (vim.opt.*)
│   ├── keymaps.lua    ← vlastní klávesy
│   └── autocmds.lua   ← autopříkazy
└── lua/plugins/
    └── *.lua          ← každý soubor = pluginové spec(y), načítá se automaticky
```

## Změnit option

Do `lua/config/options.lua`:

```lua
vim.opt.relativenumber = false   -- vypnout relativní čísla řádků
vim.opt.wrap = true              -- zalamovat dlouhé řádky
```

## Přidat keymapu

Do `lua/config/keymaps.lua`:

```lua
vim.keymap.set("n", "<leader>w", "<cmd>w<cr>", { desc = "Uložit" })
```

`desc` není okrasa — díky němu se klávesa ukáže ve which-key nabídce.

## Přidat plugin

Nový soubor `lua/plugins/table-mode.lua`:

```lua
return {
  { "dhruvasagar/vim-table-mode", ft = "markdown" },
}
```

`ft = "markdown"` = načte se líně, až u Markdown souboru. Po uložení `:Lazy` → `I`
(install). Přesně takhle si přidáš auto-zarovnávání tabulek z receptu
[Markdown](markdown-v-neovim.md).

## Upravit existující plugin

Stejné jméno + `opts` — LazyVim je chytře sloučí s výchozími:

```lua
return {
  { "folke/tokyonight.nvim", opts = { style = "moon" } },
}
```

## Vypnout plugin, který nechceš

```lua
return {
  { "akinsho/bufferline.nvim", enabled = false },
}
```

## Užitečné příkazy

| Příkaz | Co |
|--------|-----|
| `:Lazy` | UI správce pluginů — update `U`, install `I`, profil startu `P` |
| `:LazyExtras` | kurátorované balíčky (jazyky, DAP, AI…) |
| `:LazyHealth` | kontrola, že nic nechybí |

## Zásady, ať se nerozbiješ

- **Nikdy needituj** soubory LazyVim samotného — všechno jde přes spec v `lua/plugins/`.
- Jeden tematický soubor na věc (`markdown.lua`, `colors.lua`) — snáz se to čistí.
- Config si verzuj gitem (`~/.config/nvim` jako repo) — na druhý Mac pak jen clone.

## Cvičení
- [ ] Přidej si keymapu s `desc` a najdi ji ve which-key.
- [ ] Nainstaluj `vim-table-mode` přes vlastní spec a ověř v `:Lazy`.
- [ ] Přepni tokyonight na `style = "moon"` (a klidně zpět).
- [ ] Projdi `:LazyHealth`.
