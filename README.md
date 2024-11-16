# fzf-code

Use [`fzf`](https://github.com/junegunn/fzf), [`ripgrep`](https://github.com/BurntSushi/ripgrep), [`bat`](https://github.com/sharkdp/bat), and [`xargs`](https://www.man7.org/linux/man-pages/man1/xargs.1.html) to open selected files to [`code`](https://github.com/microsoft/vscode).

## Install

1. Download `fzf-code`.

   ```sh
   wget github.com/Arnesfield/fzf-code/raw/main/fzf-code -O fzf-code
   ```

2. Make executable.

   ```sh
   chmod +x fzf-code
   ```

3. Make sure `fzf-code` is visible in `PATH`.

## Setup as VS Code Keyboard Shortcut

Add to `keybindings.json`:

```json
[
  // ...
  {
    // change to your desired shortcut
    "key": "ctrl+l",
    "command": "runCommands",
    "args": {
      "commands": [
        // create terminal in editor area
        "workbench.action.createTerminalEditor",
        // run fzf-code and press enter
        // use `exit 0` to always close terminal
        {
          "command": "workbench.action.terminal.sendSequence",
          "args": { "text": "fzf-code; exit 0\u000D" }
        }
      ]
    }
  }
]
```
