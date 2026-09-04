# Sublime Column Select

This plugin provides an alternate behavior for Sublime keyboard column selection.  The differences are:

* Allows reversing direction (go down too far, just go back up).
* Added PageUp/PageDown, Home/End, and mouse selection.
* Skip rows that are too short.
* If you start at the end of a line, then it will stay at the end of each line.

![example](demo1.gif)


## Installation

### By Package Control

1. Download & Install **`Sublime Text 3`** (https://www.sublimetext.com/3)
1. Go to the menu **`Tools -> Install Package Control`**, then,
    wait few seconds until the installation finishes up
1. Now,
    Go to the menu **`Preferences -> Package Control`**
1. Type **`Add Channel`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    input the following address and press <kbd>Enter</kbd>
    ```
    https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
    ```
1. Go to the menu **`Tools -> Command Palette...
    (Ctrl+Shift+P)`**
1. Type **`Preferences:
    Package Control Settings – User`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    find the following setting on your **`Package Control.sublime-settings`** file:
    ```js
    "channels":
    [
        "https://packagecontrol.io/channel_v3.json",
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
    ],
    ```
1. And,
    change it to the following, i.e.,
    put the **`https://raw.githubusercontent...`** line as first:
    ```js
    "channels":
    [
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
        "https://packagecontrol.io/channel_v3.json",
    ],
    ```
    * The **`https://raw.githubusercontent...`** line must to be added before the **`https://packagecontrol.io...`** one, otherwise,
      you will not install this forked version of the package,
      but the original available on the Package Control default channel **`https://packagecontrol.io...`**
    > [!WARNING]
    > Placing this custom channel before the default channel changes Package Control's resolution globally. Packages from this channel with the same name will override versions from the default channel.
    >
    > You can review the channel contents here:
    > https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
1. Now,
    go to the menu **`Preferences -> Package Control`**
1. Type **`Install Package`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    search for **`ColumnSelect`** and press <kbd>Enter</kbd>

See also:

1. [ITE - Integrated Toolset Environment](https://github.com/evandrocoan/ITE)
1. [Package control docs](https://packagecontrol.io/docs/usage) for details.


## Usage
By default it uses the default keystroke for column selection, plus a few extras.  These keystrokes will select the same column in the next or previous line, page (the visible region of the file), or until the beginning/end of the file.

Command | Mac | Windows | Linux
------- | --- | ------- | -----
Up | Ctrl + Shift + Up | Ctrl + Alt + Up | Alt + Shift + Up
Down | Ctrl + Shift + Down | Ctrl + Alt + Down | Alt + Shift + Down
Page Up | Ctrl + Shift + PageUp | Ctrl + Alt + PageUp | Alt + Shift + PageUp
Page Down | Ctrl + Shift + PageDown | Ctrl + Alt + PageDown | Alt + Shift + PageDown
Beginning of file | Ctrl + Shift + Home | Ctrl + Alt + Home | Alt + Shift + Home
End of file | Ctrl + Shift + End | Ctrl + Alt + End | Alt + Shift + End
Select to mouse cursor | Ctrl + Shift + Right-click | Ctrl + Alt + Right-click | Ctrl + Alt + Right-click

### Custom Keystrokes

If you want to use a different keystroke, go to "Preferences" then "Key Bindings - User", and add an entry like this:

	{ "keys": ["ctrl+alt+up"], "command": "column_select", "args": {"by": "lines", "forward": false}},
	{ "keys": ["ctrl+alt+down"], "command": "column_select", "args": {"by": "lines", "forward": true}},
	{ "keys": ["ctrl+alt+pageup"], "command": "column_select", "args": {"by": "pages", "forward": false}},
	{ "keys": ["ctrl+alt+pagedown"], "command": "column_select", "args": {"by": "pages", "forward": true}},
	{ "keys": ["ctrl+alt+home"], "command": "column_select", "args": {"by": "all", "forward": false}},
	{ "keys": ["ctrl+alt+end"], "command": "column_select", "args": {"by": "all", "forward": true}},

Do not include the trailing comma if it is the last entry.

## Contact
If you find a bug, or have suggestions, head over to the github page:
https://github.com/ehuss/Sublime-Column-Select
