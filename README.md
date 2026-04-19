# Neovim Configuration

A web-focused Neovim configuration based on [kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim) at [9b4fbc5](https://github.com/nvim-lua/kickstart.nvim/commit/9b4fbc5021551188965d7cba54874fd1496d6ed2), optimized for web development (HTML, CSS, JavaScript, TypeScript, Svelte, Astro, TailwindCSS).

---

## Installation

### 1. System Dependencies (Required)

```bash
# Core requirements
brew install neovim    # v0.12+ required

# For Treesitter parsing and compilation
brew install tree-sitter-cli
```

### 2. Fonts (Required)

Install a [Nerd Font](https://www.nerdfonts.com/) for icons:

```bash
brew install --cask font-jetbrains-mono-nerd-font
# or
brew install --cask font-fira-code-nerd-font
```

Then set your terminal to use the installed font.

### 3. Clone and Start

```bash
# Backup existing config
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak
mv ~/.local/state/nvim ~/.local/state/nvim.bak
mv ~/.cache/nvim ~/.cache/nvim.bak

# Clone this config
git clone <your-repo> ~/.config/nvim

# Start Neovim - plugins will auto-install on first launch
nvim
```

### 4. Post-Install Steps

Run these commands in Neovim after first launch:

```vim
" Wait for lazy.nvim to finish installing plugins, then:

" Generate help tags
:helptags ALL

" Install treesitter parsers (auto-installs, but can force)
:TSUpdate

" Check health
:checkhealth
```

### Verify Installation

```vim
:checkhealth
```

All checks should pass. Common fixes:
- Missing CLI tools: `brew install <tool>`
- Treesitter errors: `:TSUpdate`
- LSP not working: `:LspInfo` and `:Mason`

---

## Plugins

| Plugin | Description |
|-------|-------------|
| [vim-be-better](https://github.com/szymonwilczek/vim-be-better) | Better Vim improvements |
| [guess-indent.nvim](https://github.com/NMAC427/guess-indent.nvim) | Auto-detect indentation |
| [nvim-web-devicons](https://github.com/nvim-tree/nvim-web-devicons) | File icons |
| [gitsigns.nvim](https://github.com/lewis6991/gitsigns.nvim) | Git integration |
| [which-key.nvim](https://github.com/folke/which-key.nvim) | Keybindings popup |
| [snacks.nvim](https://github.com/folke/snacks.nvim) | Dashboard, picker, terminal |
| [persistence.nvim](https://github.com/folke/persistence.nvim) | Session persistence |
| [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) | LSP client |
| [mason.nvim](https://github.com/mason-org/mason.nvim) | LSP tools installer |
| [mason-lspconfig.nvim](https://github.com/mason-org/mason-lspconfig.nvim) | Mason + LSP bridge |
| [mason-tool-installer.nvim](https://github.com/WhoIsSethDaniel/mason-tool-installer.nvim) | Auto-install tools |
| [fidget.nvim](https://github.com/j-hui/fidget.nvim) | LSP progress UI |
| [conform.nvim](https://github.com/stevearc/conform.nvim) | Formatters |
| [improved-search.nvim](https://github.com/backdround/improved-search.nvim) | Enhanced search |
| [blink.cmp](https://github.com/saghen/blink.cmp) | Autocomplete |
| [tokyonight.nvim](https://github.com/folke/tokyonight.nvim) | Colorscheme |
| [todo-comments.nvim](https://github.com/folke/todo-comments.nvim) | TODO highlights |
| [mini.nvim](https://github.com/nvim-mini/mini.nvim) | Mini plugins suite |
| [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter) | Syntax highlighting |
| [nvim-treesitter-textobjects](https://github.com/nvim-treesitter/nvim-treesitter-textobjects) | textobjects |

---

## What Gets Auto-Installed

### Via Mason (LSP/Linters/Formatters)

| Category    | Tools                                                                         |
|------------|------------------------------------------------------------------------------|
| LSP Servers | lua_ls, vtsls, svelte, jsonls, cssls, cssmodules_ls, emmet_language_server, html, astro, tailwindcss |
| Linters    | eslint, luacheck, markdownlint, yamllint, jsonlint, htmlhint, stylelint        |
| Formatters  | stylua, prettier                                                        |

### Via Treesitter

Parsers for: bash, lua, vim, javascript, typescript, tsx, svelte, json, html, markdown, markdown_inline, css, scss, yaml, toml

---

## Keybindings

**Leader key:** `<Space>`

### Essential (No Prefix)

| Key | Action |
|-----|--------|
| `<C-s>` | Save file |
| `<C-h/j/k/l>` | Navigate windows |
| `<C-d>` | Scroll half page down and center |
| `<C-u>` | Scroll half page up and center |
| `<Esc>` | Clear search highlight |
| `ga` | Switch to last buffer |
| `gV` | Select last pasted text |

### Quick Access (Leader)

| Key | Action |
|-----|--------|
| `<leader><Space>` | Find files |
| `<leader>/` | Grep |
| `<leader>ff` | Find files |
| `<leader>fr` | Recent files |
| `<leader>fc` | Config files |
| `<leader>fp` | Projects |
| `<leader>fz` | Zoxide |
| `<C-/>` | Terminal |

### Buffers (`<leader>b`)

| Key | Action |
|-----|--------|
| `<leader>bb` | Buffers list |
| `<leader>bd` | Delete buffer |
| `<leader>bo` | Delete other buffers |
| `<leader>b/` | Grep buffers |
| `<leader>bD` | Delete buffer and window |

### Code (`<leader>=`, `<leader>cf`)

| Key | Action |
|-----|--------|
| `<leader>=` | Format buffer |
| `<leader>cf` | Format buffer |

### Diagnostics (`<leader>d`)

| Key | Action |
|-----|--------|
| `<leader>dd` | Workspace diagnostics |
| `<leader>db` | Buffer diagnostics |
| `<leader>dt` | Trouble (workspace) |
| `<leader>dT` | Trouble (buffer) |
| `<leader>dq` | Quickfix list |
| `<leader>dl` | Location list |

### Files (`<leader>f`)

| Key | Action |
|-----|--------|
| `<leader>ff` | Find files |
| `<leader>fr` | Recent files |
| `<leader>fc` | Config files |
| `<leader>fe` | Explorer |
| `<leader>fp` | Projects |
| `<leader>fz` | Zoxide |
| `<leader>f.` | Find files in current directory |

### Git (`<leader>g`)

| Key | Action |
|-----|--------|
| `<leader>gs` | Git status |
| `<leader>gf` | Git files |
| `<leader>gl` | Git log (line) |
| `<leader>gC` | Git commits |
| `<leader>gc` | Git commits (file) |
| `<leader>gb` | Branches |
| `<leader>gS` | Git stash |

### Git Hunks (`<leader>gh`)

| Key | Action |
|-----|--------|
| `<leader>ghp` | Preview hunk |
| `<leader>ghP` | Preview hunk inline |
| `<leader>ghs` | Stage hunk |
| `<leader>ghu` | Undo stage hunk |
| `<leader>ghr` | Reset hunk |
| `]h` / `[h` | Next/Prev hunk |

### LSP

| Key | Action |
|-----|--------|
| `grn` | Rename |
| `gra` | Code action |
| `grD` | Goto declaration |
| `<leader>th` | Toggle inlay hints |

### Markdown (`<leader>m`)

| Key | Action |
|-----|--------|
| `<leader>mp` | Preview in browser |
| `<leader>mr` | Toggle render in buffer |

### Notifications (`<leader>n`)

| Key | Action |
|-----|--------|
| `<leader>nn` | Notification history |
| `<leader>nd` | Dismiss all |

### Search (`<leader>s`)

| Key | Action |
|-----|--------|
| `<leader>sg` | Grep |
| `<leader>sw` | Search word |
| `<leader>sb` | Grep buffers |
| `<leader>sl` | Buffer lines |
| `<leader>sh` | Help |
| `<leader>sm` | Marks |
| `<leader>sj` | Jumps |
| `<leader>sk` | Keymaps |
| `<leader>sc` | Command history |
| `<leader>sC` | Commands |
| `<leader>s:` | Command history |
| `<leader>s/` | Search history |
| `<leader>sq` | Quickfix list |
| `<leader>sr` | Registers |
| `<leader>sR` | Resume |
| `<leader>su` | Undo history |
| `z=` | Spelling suggestions |

### UI/Toggles (`<leader>u`)

| Key | Action |
|-----|--------|
| `<leader>uw` | Toggle wrap |
| `<leader>ul` | Toggle relative numbers |
| `<leader>uT` | Toggle treesitter |
| `<leader>uS` | Toggle scroll |

### Windows (`<leader>w`)

| Key | Action |
|-----|--------|
| `<leader>wd` | Close window |
| `<leader>ws` | Split horizontal |
| `<leader>wv` | Split vertical |
| `<leader>ww` | Other window |
| `<leader>w=` | Equal size |
| `<leader>wm` | Maximize |

### Goto (`g`)

| Key | Action |
|-----|--------|
| `gd` | Definition |
| `gD` | Declaration |
| `gr` | References |
| `gi` | Implementation |
| `gy` | Type definition |

### Navigation (`[` / `]`)

| Key | Action |
|-----|--------|
| `[d` / `]d` | Prev/Next diagnostic |
| `[h` / `]h` | Prev/Next hunk |
| `[b` / `]b` | Prev/Next buffer |
| `[[` / `]]` | Prev/Next reference |

### Editing

| Key | Mode | Action |
|-----|------|--------|
| `J` / `K` | Visual | Move lines down/up |
| `<` / `>` | Visual | Indent (stay selected) |
| `p` | Visual | Paste (no yank) |
| `X` | Normal | Split line |
| `YY` | Normal | Yank block {} |
| `n` / `N` | Normal | Next/Prev match (centered) |

### Surround (mini.surround)

| Key | Action |
|-----|--------|
| `gsa` | Add surrounding |
| `gsd` | Delete surrounding |
| `gsr` | Replace surrounding |
| `gsf` | Find surrounding (right) |
| `gsF` | Find surrounding (left) |

---

## Language Servers (Mason)

Auto-installed:
- **Lua:** lua_ls
- **TypeScript/JavaScript:** vtsls
- **Svelte:** svelte
- **JSON:** jsonls
- **CSS:** cssls, cssmodules_ls
- **HTML:** html, emmet_language_server
- **Astro:** astro
- **TailwindCSS:** tailwindcss

## Formatters (Conform)

| Language | Formatter |
|----------|-----------|
| Lua | stylua |
| JavaScript/TypeScript | prettier |
| HTML/CSS/JSON/YAML/Markdown | prettier |

Format on save is **enabled by default**.

## Linters (nvim-lint)

| Language | Linter |
|----------|--------|
| JavaScript/TypeScript | eslint |
| Lua | luacheck |
| Markdown | markdownlint |
| YAML | yamllint |
| JSON | jsonlint |
| HTML | htmlhint |
| CSS | stylelint |

---

## Health Check

```vim
:checkhealth
```

Common fixes:
- Missing tools: `brew install <tool>`
- Treesitter errors: `:TSUpdate`

---

Always a WIP.
