# Learn VIM Shortcuts

- `/{pattern}` searches forwards... `n/N` go to next / previous occurrence.
- `?{pattern}` searches backwards
- `gd` jump to definition
- `gf` jump to file
- `%` jump to matching `({[]})`
- `ctrl+y|e|u|d` move viewport down, up (extra lines), half a screen up, half a screen down
- use `ge` to jump to the end of a word backwards
- `gi` puts you into insert mode at the last place you made a change
- `CTRL-h` (insert mode) deletes last character typed
- `CTRL-w` (insert mode) deletes last word typed
- `CTRL-u` (insert mode) deletes last line typed
- `CTRL+h|j|k|l` focus editor left/down/up/right
- `CTRL+CMD+h|j|k|l` move editor to next/previous group
- `<number>G` go to line
- `shift+s` edit at correct indentation
- `<<|>>` unindent/indent
- `ct<letter>` change to letter
- `:m <number>` move line/selection to target
- `<leader>\||` splits editor to side/down
- `` m|'|`<letter> `` mark letter, move to mark line, move to mark line + col
- `zc|C|o|O` fold / fold all / unfold / unfold all
- `gn`:
  - if you are on top a search match, it selects the match in visual mode
  - if you are in visual mode, it extends your current selection until the end of the next match
  - if you are in operator pending mode, it operates on the next match.

example of `deleting:

- start searching using `/foo`
- delete using `dgn`
- apply to next match using `.`

## Yanking

- `yl|w|s` yanks letter/word/sentence
- `yaw|s` yanks a word/sentence including whitespace
- `"ay<motion>"` yanks to a specific register
- `"ap<motion>"` pastes from a specific register
- `p|P` pastes something after/before cursor
- `gp`/`gP` same as `p`/`gP` but puts cursor after
- `:<start>,<end>y<enter>` yank some lines

## sneak

`s<letter><letter>` searches for 2 letter combo

## EasyMotion

- `<leader><leader>s<char>` search character
- `<leader><leader>f<char>` / `<leader><leader>F<char>` find character forwards/backwards
- `<leader><leader>w`/`<leader><leader>b` start of word forwards/backwards
- `<leader><leader>j`/`<leader><leader>k` start of line forwards/backwards

## vim-surround

- `c|d|ys<motion>` change/delete/add surround
- `S` add surround in visual mode

## VSCode Specifics

- `af` visual mode command which selects increasingly large blocks of text
- `gh` hover mouse over cursor
- `gb` adds another cursor on the next word it finds which is the same as the word under the cursor
- `gd` go to definition
- `gq` on a visual selection reflow and wordwrap blocks of text, preserving commenting style. Great for formatting documentation comments.

## Command Mode

- Registers: `%` represents whole file (e.g `%d` to delete whole file)
- `0` represents beginning of the file, e.g. `:0,+10d` to delete first 10 lines
- `$` represents end of file, e.g. `:.,$d' to delete from current line to end of file

### Substituting Text

```text
:[range]s/{pattern}/{substitute}/{flags}
```

### VSCode Custom Shortcuts

in the examples below, `<leader>` corresponds to leader, ie.

- `<leader>t` toggle sidebar sidebar
- `<leader>f` find in explorer
- `<leader>r(f|s|o)` rename file/occurrences/symbol/ start linked editing
- `<leader>yj|k|y` copy lines down / lines up / selection
- `<leader>w` / `<leader>W` split editor / split editor down
- `ctrl+up|down` add cursor above/below
- `<leader>tt|n|p|o|x` new/next/prev/only/close tab
- `J|K` move up and down faster
- `<leader>/` remove highlighting from search
- `gc|C` toggle line/block comment
- `<leader>w|e|b` move (camelCase/snake_case word segment)
- `<operator>i<leader>w` select/change/delete/etc the current camelCase or snake_case word segment
- `<leader>p` show commands
- `<leader>o` quick open
- `<leader>t` go to symbol
- `<leader>h|l` go to first/last character of line (shift+`H`) for column `0`
- `<leader>n` new file
- `<leader>[|]` go to next/previous problem
- `<leader>c` copy
- `<leader>va` select all

### Combos

- Multiple cursors down: `ctrl+v` :arrow_forward: `jjjjjj` :arrow_forward: `I` :arrow_forward: (edit)

### Macros

- `q<register><commands>q` record a macro at register
- `<number>@<register>` - execute macro at register `number` times
