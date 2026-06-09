
# Neovim Configuration Guide


* Native `vim.pack` plugin management
* LSP + formatting + linting
* Treesitter
* FZF searching
* Git integration
* File explorer
* Floating terminal
* Buffer management (Barbar)
* Minimal UI with transparency
* Strong keyboard-driven workflow

---

## Philosophy

This configuration is designed for:

* Fast startup
* Minimal dependencies
* Native Neovim APIs
* IDE-like features without heavy frameworks
* Keyboard-first navigation

Features include:

* LSP
* Formatting
* Diagnostics
* Treesitter syntax highlighting
* Git integration
* Fuzzy finding
* File explorer
* Floating terminal
* Buffer tabs
* Persistent undo

---

# Installation Requirements

## Neovim

Requires a recent Neovim version supporting:

* `vim.pack`
* `vim.lsp.config`
* modern Treesitter APIs

Recommended:

```bash
nvim --version
```

Neovim 0.11+.

---

## Nerd Font

Statusline and UI use Nerd Font icons.

Recommended fonts:

* JetBrainsMono Nerd Font
* FiraCode Nerd Font
* Hack Nerd Font

---

## External Tools

### Lua

```bash
luacheck
stylua
```

### Python

```bash
flake8
black
```

### JavaScript / TypeScript

```bash
eslint_d
prettier_d
```

### Shell

```bash
shellcheck
shfmt
```

### Go

```bash
gofumpt
revive
```

### C / C++

```bash
clang-format
cpplint
```

---

# UI

## Transparent Theme

The configuration automatically removes backgrounds from:

* editor
* statusline
* tabs
* floating windows
* sign column

Theme:

```lua
tokyonight-storm
```

---

## Statusline

Shows:

* Current mode
* File name
* Git branch
* File type
* File size
* Cursor position

Inactive windows get a simplified statusline.

---

# Basic Navigation

## Movement

### Wrapped-line aware movement

```text
j
k
```

Behave intelligently:

* move visual lines when no count is given
* move real lines when count is used

Examples:

```text
j
5j
```

---

## Center Cursor During Navigation

### Search

```text
n
N
```

Automatically centers screen.

### Half-page movement

```text
Ctrl-d
Ctrl-u
```

Automatically centers screen.

---

# Search

## Clear Search Highlighting

```text
<leader>c
```

Leader:

```text
Space
```

So:

```text
Space c
```

---

# Window Management

## Move Between Windows

```text
Ctrl-h
Ctrl-j
Ctrl-k
Ctrl-l
```

---

## Create Splits

Vertical:

```text
Space sv
```

Horizontal:

```text
Space sh
```

---

## Resize Windows

```text
Ctrl-Up
Ctrl-Down
Ctrl-Left
Ctrl-Right
```

---

# Buffers

## Basic Buffer Navigation

Next:

```text
Space bn
```

Previous:

```text
Space bp
```

---

# Barbar Buffer Tabs

## Navigate

Previous:

```text
Alt-,
```

Next:

```text
Alt-.
```

---

## Jump to Buffer

```text
Alt-1
Alt-2
...
Alt-9
Alt-0
```

---

## Pin Buffer

```text
Alt-p
```

---

## Close Buffer

```text
Alt-c
```

---

## Pick Buffer

```text
Ctrl-p
```

Delete by picking:

```text
Ctrl-Shift-p
```

---

# File Explorer

Plugin:

```text
nvim-tree
```

Toggle:

```text
\
```

---

# Fuzzy Finding

Plugin:

```text
fzf-lua
```

## Files

```text
Space ff
```

---

## Live Grep

```text
Space fg
```

---

## Buffers

```text
Space fb
```

---

## Help

```text
Space fh
```

---

## Diagnostics

Current file:

```text
Space fx
```

Workspace:

```text
Space fX
```

---

# Git

Plugin:

```text
gitsigns.nvim
```

---

## Hunk Navigation

Next:

```text
]h
```

Previous:

```text
[h
```

---

## Stage Hunk

```text
Space hs
```

---

## Reset Hunk

```text
Space hr
```

---

## Preview Hunk

```text
Space hp
```

---

## Blame Line

```text
Space hb
```

---

## Toggle Inline Blame

```text
Space hB
```

---

## Diff Current File

```text
Space hd
```

---

# LSP

Configured servers:

| Language   | Server  |
| ---------- | ------- |
| Lua        | lua_ls  |
| Python     | pyright |
| Bash       | bashls  |
| TypeScript | ts_ls   |
| Go         | gopls   |
| C/C++      | clangd  |

---

# LSP Navigation

Definition (FZF):

```text
Space gd
```

Direct definition:

```text
Space gD
```

Definition in split:

```text
Space gS
```

---

## References

```text
Space fr
```

---

## Implementations

```text
Space fi
```

---

## Type Definitions

```text
Space ft
```

---

## Document Symbols

```text
Space fs
```

---

## Workspace Symbols

```text
Space fw
```

---

# Refactoring

Rename:

```text
Space rn
```

Code Action:

```text
Space ca
```

---

# Diagnostics

Cursor diagnostic:

```text
Space d
```

Current line:

```text
Space D
```

Next:

```text
Space nd
```

Previous:

```text
Space pd
```

List all:

```text
Space q
```

---

# Formatting

Formatting occurs automatically on save when:

1. Buffer is a real file
2. Buffer is modifiable
3. `efm` LSP is attached

Supported:

* Lua
* Python
* JS/TS
* HTML/CSS
* Shell
* Go
* C/C++

---

# Completion

Plugin:

```text
blink.cmp
```

Open menu:

```text
Ctrl-Space
```

Accept:

```text
Enter
```

Next item:

```text
Ctrl-j
```

Previous item:

```text
Ctrl-k
```

---

# Snippets

Forward:

```text
Tab
```

Backward:

```text
Shift-Tab
```

---

# Terminal

Floating terminal:

```text
Space t
```

Features:

* centered
* 80% screen size
* reusable session
* rounded border

Close terminal:

```text
Esc
```

while in terminal mode.

---

# Editing Enhancements

## Move Lines

Line down:

```text
Alt-j
```

Line up:

```text
Alt-k
```

Works in:

* Normal mode
* Visual mode

---

## Indent and Reselect

Left:

```text
<
```

Right:

```text
>
```

Selection remains active.

---

## Join Lines

```text
J
```

Preserves cursor position.

---

## Paste Without Overwriting Register

```text
Space p
```

Visual mode only.

---

## Delete Without Yanking

```text
Space x
```

---

# Utility Commands

## Copy Current File Path

```text
Space pa
```

Copies absolute path to system clipboard.

---

## Toggle Diagnostics

```text
Space td
```

Enable/disable diagnostics globally.

---

# Automatic Features

### Persistent Undo

Undo history survives restarts.

Location:

```text
~/.vim/undodir
```

---

### Restore Cursor Position

Reopens files where you left off.

---

### Yank Highlight

Copied text flashes briefly.

---

### Markdown/Text Enhancements

Automatically enables:

* wrap
* linebreak
* spellcheck

For:

* markdown
* text
* gitcommit

---

# Plugin List

| Plugin             | Purpose            |
| ------------------ | ------------------ |
| gitsigns.nvim      | Git integration    |
| mini.nvim          | Utility modules    |
| fzf-lua            | Fuzzy finder       |
| nvim-tree          | File explorer      |
| nvim-treesitter    | Syntax parsing     |
| nvim-lspconfig     | LSP                |
| mason.nvim         | Tool management    |
| efmls-configs-nvim | Formatting/linting |
| blink.cmp          | Completion         |
| LuaSnip            | Snippets           |
| tokyonight.nvim    | Theme              |
| emmet-vim          | HTML expansion     |
| smear-cursor.nvim  | Cursor animation   |
| barbar.nvim        | Buffer tabs        |
| nvim-web-devicons  | Icons              |

---

## Efficiency Tips

For maximum speed, memorize these first:

| Action            | Key        |
| ----------------- | ---------- |
| Find file         | `Space ff` |
| Grep project      | `Space fg` |
| Toggle tree       | `\`        |
| Definition        | `Space gd` |
| References        | `Space fr` |
| Code action       | `Space ca` |
| Rename            | `Space rn` |
| Floating terminal | `Space t`  |
| Next git hunk     | `]h`       |
| Previous git hunk | `[h`       |
| Next buffer       | `Alt-.`    |
| Previous buffer   | `Alt-,`    |

These 12 commands cover roughly 90% of day-to-day development workflows with your configuration.

