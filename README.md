# What is this for?

This is a configuration file for [GokuRakuJoudo](#what-are-karabiner-and-gokurakujoudo) which in turn generates a [Karabiner](#what-are-karabiner-and-gokurakujoudo) profile.

With sequences and squeezing up to 4 events out of a single key, it enables you to limit the number of times you need to twist your hands or are forced to leave the home row. Sequence layers transform chords like `Cmd+Key`, `Shift+Key`, `Ctrl+Key` into sequences of pressing two keys. For example, instead of pressing `Cmd+S` to save a file, you can press `Cmd` quickly followed by `S` and get the same behavior. `Cmd` still retains its original behavior and can be used for any `Cmd+Key` combo.

**WARNING**: Some things rely upon the fact that the Colemak layout (and its corresponding layer) is used. As such, the semicolon key on Colemak (where P is placed on QWERTY) is unmapped in the default layout and is instead used as a "power key" and a trigger for the power layer. This key is then mapped per-app: toggle reader mode in Safari, switch between editor and terminal in VSCode or send the tmux prefix in [Kitty](https://sw.kovidgoyal.net/kitty/index.html), the fast, lightweight, terminal emulator.

## What are Karabiner and GokuRakuJoudo?

[Karabiner](https://pqrs.org/osx/karabiner/) is a powerful and stable keyboard customizer for macOS. [Goku](https://github.com/yqrashawn/GokuRakuJoudo) is a tool to let you manage your Karabiner configuration with ease, since Karabiner uses JSON for its very verbose, complex config file, while Goku uses the "optimized for typing" [edn format](https://github.com/edn-format/edn).

## Background

The idea of the sequence layers was inspired by Xah Lee's [article](http://xahlee.info/kbd/banish_shift_key.html) on banning the Shift key, thus avoiding combos of multiple key presses (chording) as much as possible. Triggering some things on double-press and hold or on double-press and release, you can get 4 events on a single key such as command, caps lock and others. Some of the combos defined are specific to my [60% Velocifire M2](https://www.velocifiretech.com/product/m2-wireless-mechanical-keyboard/) keyboard, making it a lot more usable without having to resort to chording for most of the right-side modifiers which overlap with arrows by default.

### Functional Summary

#### Sequence Layers

- **symbols** (type "`LShift` followed by `Key`" to get symbols like !, *, parens, etc)
- **shifted** (type "`RShift` followed by `Key`" to get capital letter for `Key`)
- **emoji** (while in the shifted layer, type `LShift` then various letters to get emojis)
- **ctrl** (type "`LCtrl` followed by `Key`" to get `LCtrl+Key`)
- **command** (type "`LCmd` followed by `Key`" to get `LCmd+Key`)

#### App-Specific Layers

- **kitty** (customizations for [Kitty](https://sw.kovidgoyal.net/kitty/index.html), the fast, lightweight, terminal emulator)
- **vscode** (customizations for Visual Studio Code)
- **safari** (customizations for Safari)

#### Chording Layers

- **extend** (type `CapsLock` and hold to activate, quick release for `Esc`)
- **power** (a second extend layer, application specific. hold Colemak `semicolon` to activate, quickly release to just press the power key)
- **apps** (press and hold `A`, then quickly follow by various keys to switch to apps)
- **desktop** (press and hold `F`, then quickly follow by various keys to switch to desktop)
- **system** (press and hold `Fn` to activate and rearrange windows or other tasks, quick release to show desktop)
- **mouse** (press `LCmd` twice and hold for mouse movements or press twice and release for `LCmd+Tab`)

## Installation

1. Install [Karabiner-Elements](https://pqrs.org/osx/karabiner/)
2. Create a profile named 'Default' in Karabiner-Elements. (It will generate a karabiner.json file under ~/.config/karabiner/ folder for goku to use.)
3. Install [Goku](https://github.com/yqrashawn/GokuRakuJoudo)
4. Install files from this repo.

```shell
# curl https://raw.githubusercontent.com/kiinoda/goku/master/karabiner.edn > ~/.config/karabiner.edn
# goku
```

### Inspiration

Various parts were adapted from other internet sources, indicated below.

- [Kun Chen - k-goku](https://github.com/kchen0x/k-goku) - document structure and general inspiration
- [John Lindquist - dotfiles](https://github.com/johnlindquist/dotfiles) - emoji layer contents and from/to templates needed to "translate" between QWERTY and Colemak
- [Nikita Voloboev - dotfiles](https://github.com/nikitavoloboev/dotfiles) - general inspiration, properly using conditions in rules
- [Xah Lee - Banning the Shift Key](http://xahlee.info/kbd/banish_shift_key.html) - the seed for the sequence layers
- [Øystein Bech Gadmar - Colemak Forum - Extend Layer](https://forum.colemak.com/topic/2014-extend-extra-extreme/) - the general organization of the extend layer

<!---
| SAMPLE TABLE DEFINITION                                                    |
| key               | effect                                                 |
|-------------------|--------------------------------------------------------|
|                   |                                                        |
|                   |                                                        |
--->
