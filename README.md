# hvoigt NeoVim Start

This is my NeoVim configuration. It is currently cobbled together from
[kickstart.vim](https://github.com/nvim-lua/kickstart.nvim), and my good old
personal [.vimrc](https://www.hvoigt.net/.vimrc) preferences.

## Installation

Install NeoVim and clone this repository as the configuration directory for
NeoVim:

```sh
brew install neovim
git clone https://github.com/hvoigt/config-nvim.git ~/.config/nvim
```

## Usage

Use `:Mason` to install all language server support needed.

This is a highly opinionated list of the additional features:

- `gr` - Show references of symbol in Telescope
- `,sf` - Fuzzy open filename in Telescope
- `,ws` - Fuzzy search all workspace symbols
- `,o` - Open location on GitHub
- `zg` - Add word to spellchecker
- `<ctrl>-i` / `m-backspace` - Incremental / Decremental Scoped selection
- `<ctrl>-k` - signature help
- `]m` / `[m` - Next/Previous function
- `<ctrl>-q` - Send Telescope result to quick-fix list
- `:Telescope keymaps` - Show/Search keybindings
- `:Telescope builtin` - Search through built-in functions
- `:Mason` - add language servers
- `:Lazy` - Install/Update

## Navigation Customizations

Additional to default Vim navigation these are some customizations

- `<tab>` - Next open buffer
- `<shift>-<tab>` - Previous open buffer
- `<space>` - Page down
- `b` - Page up

## My personal list of the most important Vim commands

### 10 most important Commands:

- `i` - Enter Insert mode (editing mode) (now you can enter text)
- `ESC` - Exit Insert mode and return to Command mode
- `:q!` - Quit without saving
- `:wq` - Save and quit
- `u` - Undo
- `C-r` - Redo
- `v` - Select character-wise
- `y` - Copy the selected text (yank)
- `d` - Cut the selected text (saves to the copy register)
- `P` - Paste the copied text from the current copy register before the current position

Here's the same information in more detail, as mentioned, these are just the *key* commands that come to mind:

### Loading, Saving, Exiting

- `:w` - Save the file
- `:wq` - Save the file and exit Vim
- `:q` - Exit
- `:q!` - Exit even if not everything is saved
- `:w!` - Try to save even if read-only
- `:e <File>` - Open `<File>` for editing

### Switching From Command to Insert Mode

- `o` - Open a new line below the current line for editing
- `O` - Open a new line above the current line for editing
- `i` - Enter insert mode at the current position
- `a` - Enter insert mode after the current character
- `A` - Enter insert mode at the end of the line
- `cw` - Delete from the cursor position to the end of the word and switch to edit mode

### In Insert Mode

- `C-n` - Auto-complete forward (press multiple times to cycle through suggestions)
- `C-p` - Auto-complete backward (press multiple times to cycle through suggestions)
- `ESC` - Exit insert mode and return to Command mode

### Selecting

- `v` - Select character-wise
- `V` - Select line-wise
- `C-v` - Select block-wise

You can apply many commands to selections. With a selection, you can perform the following commands:

- `d` - Cut the selected text (saves to the copy register)
- `y` - Copy the selected text (yank)
- `:` - Apply a command to the selection (e.g., `:s/bla/blub/` to replace all occurrences of "bla" with "blub")
- `:w` - Save the selection to a file
- `:sort` - Alphabetically sort the lines in the selection
- `=` - Automatically format (indent) the selection
- `gq` - Reformat the selection (useful for rewrapping text if you added something in between)

### Editing (Command mode)

_NOTE: If you select line-wise, pasting will also work line-wise_

- `dd` - Delete a line
- `.` - Repeat the last action
- `u` - Undo
- `C-r` - Redo
- `D` - Delete from the current position to the end of the line
- `p` - Paste the text from the current copy register after the current position
- `P` - Paste the text from the current copy register before the current position
- `==` - Automatically format the line

### Navigation

- `0,$` - Go to the beginning, end of the line
- `:0,:$` - Go to the beginning, end of the file
- `:<Number>` - Go to line `<Number>`
- `h,j,k,l` - Move the cursor left, down, up, right
- `C-u` - Scroll up by one page
- `C-d` - Scroll down by one page
- Searching: _Search terms can be retrieved from the history using the cursor keys_
  - `/<Term>` - Search down for `<Term>`
  - `?<Term>` - Search up for `<Term>`
- `n` - Jump to the next occurrence of the last search
- `N` - Jump to the previous occurrence of the last search
- `*` - Search forward for the word under the cursor and jump to it
- `#` - Search backward for the word under the cursor and jump to it
- `E` - Jump to the next space
- `B` - Jump to the previous space
- `%` - Bracket matching: Jump from an opening bracket to its closing counterpart and vice versa

### Compiling

- `:make` - Run `make` in the current directory
- `:copen` - Open a new window with the compiler output. Press Enter on a warning/error to jump to that location automatically.

### Windows

- `C-w <left>,<up>,<down>,<right>` - Jump to a window on the left, up, down, or right of the current one
- `C-w` - Jump to the window above
- `C-w n` - Create a new window above
- `C-w v` - Create a new window beside
- `C-w c` - Close the current window

### Buffers

- `:bnext` - Switch to the next buffer (mapped to `<Tab>` in my .vimrc)
- `:bprevious` - Switch to the previous buffer (mapped to `<Shift>`+`<Tab>` in my .vimrc)
- `:bdelete` - Close the buffer

## Tips

### Debugging Language Server Configuration

- `:lua vim.cmd('e'..vim.lsp.get_log_path())` - LSP logs

### C/C++ Code

- `bear -- make` - generates a `compile-commands.json`  for `clangd` so `gI` (go to Implementation works)
