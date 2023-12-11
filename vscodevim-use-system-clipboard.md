# vscodevim Use System Keyboard

vscodevim does not automatically use the system clipboard. But we can edit the `user settings` in vscode to make this possible.

Open the command pallete: `Ctrl + Shift + p`. Search for `Preferences: Open User Settings (JSON)`. Add the following setting to the file:

```json
"vim.useSystemClipboard": true,
```

## References

[VSCode Vim Use System Clipboard](https://stackoverflow.com/questions/58306002/vs-code-vim-extension-copy-and-paste)



