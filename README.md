# What is this for?

This is a configuration file for [GokuRakuJoudo](#what-are-karabiner-and-gokurakujoudo) which in turn generates a [Karabiner](#what-are-karabiner-and-gokurakujoudo) profile.

Some things rely upon the fact that the Colemak layout (and its corresponding layer) is used. Single press mod keys are used as "power key combos" and a trigger things like toggling reader mode in Safari, switching between editor and terminal in VSCode or sending the tmux prefix in [Kitty](https://sw.kovidgoyal.net/kitty/index.html), the fast, lightweight, terminal emulator.

## What are Karabiner and GokuRakuJoudo?

[Karabiner](https://pqrs.org/osx/karabiner/) is a powerful and stable keyboard customizer for macOS. [Goku](https://github.com/yqrashawn/GokuRakuJoudo) is a tool to let you manage your Karabiner configuration with ease, since Karabiner uses JSON for its very verbose, complex config file, while Goku uses the "optimized for typing" [edn format](https://github.com/edn-format/edn).

## Sample combos

- press and release `LCmd` to switch to previously used app
- press and release `RCmd` and, depending on the current app get this:
  - toggle between terminal and editor in VSCode
  - toggle reading mode in Safari
  - send tmux prefix in Kitty
  - toggle left pane with notes list in Drafts
- press and release `ROpt` and, depending on the current app get this:
  - toggle between left and right editors in split-screen VSCode
  - toggle tab overview in Safari
  - etc
- get an extended layer on pressing and holding the space bar
- etc

**Special mention**: there is an `experimental` branch where some settings are active, like sequence layers (press `shift`, quickly followed by `s` to send `S`, or `LCmd` quickly followed by `t` to send `Cmt+T`) or getting 4 different outcomes from a single key. Check it out.

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
