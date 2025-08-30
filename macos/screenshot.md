# Screenshots in macOS

## Set the default screenshot file format:

```shell
defaults write com.apple.screencapture type -string "png"
```

- Available formats: png, jpg, heic, gif, PDF, tiff
- If you choose PDF, it must be all uppercase.

## Enable / Disable screenshot shadow:

```shell
# enable
defaults write com.apple.screencapture disable-shadow -bool true

# disable
defaults write com.apple.screencapture disable-shadow -bool false
```

---

## Include date and time in the screenshot file:

```shell
# enable
defaults write com.apple.screencapture "include-date" -bool true

# disable
defaults write com.apple.screencapture "include-date" -bool false
```

- If enabled, it will include the date in the format of `YYYY-MM-DD HH.MM.SS`
- If disabled, it will use a counter, e.g. `Screenshot 1.png`, `Screenshot 2.png`, ...

---

## Set default location of screenshots:

```shell
defaults write com.apple.screencapture "location" -string "~/Downloads"
```

---

## Keyboard shortcuts:

- To take a partial screenshot of the screen where you set the dimensions with the mouse: `CMD + SHIFT + 4`. This will copy the screenshot to the clipboard.
- To take a screenshot of a single window: `CMD + SHIFT + 4` then press the space bar and select the window by clicking on it.
- To open the screenshot floating window: `CMD + SHIFT + 5`.

---

### Note

- Make sure to run `killall SystemUIServer` for the configs to take effect.

