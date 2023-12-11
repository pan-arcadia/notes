# Remap Caps and Escape Keys

In Ubuntu 22.04.3 we can map the `caps lock` to `esc` by editing `/etc/default/keyboard`.

It's a read-only file, so we need to open like this:

```shell
sudo vim /etc/default/keyboard
```

We need to set `XKBOPTIONS="caps:escape"`:

So our file should look something like this:

```shell
# KEYBOARD CONFIGURATION FILE

# Consult the keyboard(5) manual page.

XKBMODEL="pc105"
XKBLAYOUT="us"
XKBVARIANT=""
XKBOPTIONS="caps:escape"

BACKSPACE="guess"
```

We'll also need to make some edits in `vscode`. 

Open the command pallete, `ctrl + shift + p`, search for `Preferences: Open keyboard shortcuts (JSON)` (this will open `keybindings.json`). Add the following:

```json
    {
        "key": "capslock",
        "command": "extension.vim_escape",
        "when": "editorTextFocus && vim.active && !inDebugRepl"
    },
    {
        "key": "escape",
        "command": "-extension.vim_escape",
        "when": "editorTextFocus && vim.active && !inDebugRepl"
    }

```

Reload VSCode and we should be good to go.

## References

[Use capslock as escape in VSCode](https://stackoverflow.com/questions/48369303/use-in-visual-studio-code-vim-extension-caps-instead-of-esc)

[Map capslock to esc in Ubuntu](https://askubuntu.com/questions/1481214/how-to-permanently-remap-caps-lock-into-esc-key-on-ubuntu-22-04-3-with-wayland-d)

