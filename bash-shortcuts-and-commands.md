# Bash readline shortcuts and useful commands

Legend and notes:
- `C` means `Ctrl`/`Control`.
- `M` means `Alt`/`Meta`/`Option` (For Macs, with proper setting).
- `S` means `Shift`.
- `Bksp` means `Backspace`.

Note that some shortcuts use `Shift` implicitly, e.g. `M-<` is really
`Alt + Shift + ,`. There will be an additional explicit keybinding for these.

For more bash shortcuts, see `man bash` and search for `^READLINE`.


## Movement

Shortcut | Description
---------|------------
`C-f`    | Move forward a character.
`C-b`    | Move back a character.
`M-f`    | Move forward to the end of the next word. Words are composed of alphanumeric characters (letters and digits).
`M-b`    | Move back to the start of the current or previous word.  Words are composed of alphanumeric characters (letters and digits).
`C-a`    | Move to the start of the line.
`C-e`    | Move to the end of the line.


## History

Note: In order to use `C-s`, execute `stty -ixon` (add it to your `.bashrc`).

Shortcut          | Description
------------------|------------
`C-p`             | Fetch the previous command from the history list.
`C-n`             | Fetch the next command from the history list.
`M-<` (`M-S-,`)   | Move to the first line in the history.
`M->` (`M-S-.`)   | Move to the last line in the history.
`C-r`             | Incrementally search backward through the history.
`C-s`             | Incrementally search forward through the history.


## Deleting, killing and yanking

Killing is different from deleting, since it saves the killed text in the
kill-ring, from which it can be yanked (pasted) back.

Shortcut | Description
---------|------------
`Bksp`   | Delete the character behind the cursor.
`C-d`    | Delete the character at point.
`M-\`    | Delete all spaces and tabs around point.
`M-Bksp` | Kill the word behind point.
`M-d`    | Kill from point to the end of the current/next word.
`C-w`    | Kill the word behind point (different boundaries than `M-Bksp`).
`C-k`    | Kill the text from point to the end of the line.
`C-u`    | Kill backward from point to the beginning of the line.
`C-y`    | Yank the top of the kill ring at point.
`M-y`    | Rotate the kill ring, and yank the new top at point.


## Completing

Shortcut          | Description
------------------|------------
`TAB`             | Autocomplete.
`TAB-TAB`         | List possible completions.
`M-?` (`M-S-/`)   | List possible completions.
`M-*` (`M-S-8`)   | Insert possible completions.


## Batch command execution

Note: For some of these commands/shortcuts, you need to export the `EDITOR`
environment variable, setting it to a text editor executable, for example
`export EDITOR=vim`. Add the line to your `.bashrc` for permanent effect.


Shortcut          | Description
------------------|------------
`C-x C-e`         | Opens `EDITOR`. Write down commands, save and exit, and shell will execute these commands.


Command           | Description
------------------|------------
`history 100`     | Displays last 100 items from the current history.
`fc 50 60`        | Opens `EDITOR` which contains commands between 50th and 60th (inclusive). Works similarly to `C-x C-e`.


## Miscellaneous

Shortcut          | Description
------------------|------------
`C-l`             | Clear the screen.
`C-_` (`C-S--`)   | Incremental undo, separately remembered for each line.
`M-r`             | Undo all changes made to this line.
`C-t`             | Transpose character before point with character at point.
`M-t`             | Transpose word before point with word at/after point.
`M-#` (`C-S-3`)   | Comment and execute a new line.
