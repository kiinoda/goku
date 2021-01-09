This repo contains a configuration for GokuRakuJoudo which is used to generate a Karabiner profile. Various parts were adapted from other internet sources, check out the __Inspiration__ section below.


## What is Karabiner?

[Karabiner](https://pqrs.org/osx/karabiner/) is a powerful and stable keyboard customizer for macOS.

- You can re-map any key without any restriction. 
- You can accelerate speed of the key repeat. Karabiner offers frequently used settings. 

## What is GokuRakuJoudo?

[Goku](https://github.com/yqrashawn/GokuRakuJoudo) is a tool to let you manage your Karabiner configuration with ease.

Karbiner Elements uses JSON as it's config file. This leads to thousands lines of JSON (sometimes over 20,000 lines). Which makes it really hard to edit the config file and iterate on your keymap.

Goku use the [edn format](https://github.com/edn-format/edn) to the rescue.

## What does this repo contain?

You will find some regular customizations that you find elsewhere, adapted to my taste. My personal additions are as follows:

- the sequence layers
- squeezing up to 4 events out of a single key

My sequence layers transform chords like Cmd+Key, Shift+Key, Ctrl+Key into sequences of pressing two keys. For example, instead of pressing Cmd+S to save in VSCode, I instead press Cmd quickly followed by S and get the same behavior. Cmd can still be used for any Cmd+Key combination. The sequence layers where inspired by Xah Lee's [article](http://xahlee.info/kbd/banish_shift_key.html) on banning the Shift key, thus avoiding combos of multiple key presses as much as possible.

One other useful behavior that I make use of is triggering some things on double-press and hold as with the mouse layer that is on left_command. This manifests in being able to use 4 events on a single key such as command, caps lock and others, making use of layers, negated conditions and the `:alone` property when defining a rule.

I also maintain a different velocifire branch where I keep specific changes for a [60% Velocifire M2](https://www.velocifiretech.com/product/m2-wireless-mechanical-keyboard/) and make it a lot more usable.

Example One (found in the main branch):

- press and hold `Cmd` key to get usual behavior (combos like `Cmd+S`)
- press and release `Cmd` key to trigger command layer (effectively getting `Cmd+S` if you press `Cmd` quickly followed by `S`)
- press twice and hold `Cmd` key to trigger mouse layer (use the mouse, press `Caps` to slow it down)
- press twice and then release `Cmd` key to trigger things (`Cmd+Tab`, switch between editor and terminal in VSCode, whatever)

Example Two (used verbatim in the velocifire branch):

- press and hold `LShift` to get usual behavior (combos like `LShift+A`)
- press and release `LShift` to trigger __symbols__ layer (quickly following `LShift` by `a` gives you `@`, etc)
- press twice and release `LShift` to get `:`

Example Three (a variation of this is used in both the main and velocifire branches):

- press and hold `RShift` to get usual behavior (combos like `RShift+A`)
- press and release `RShift` to trigger shifted layer (quickly following `RShift` by `a` gives you `A`, etc)
- press and release `RShift` to trigger shifted layer, then press `LShift` and you're in the emoji layer
- press twice and release `RShift` to get `?`

The sky is the limit!

### Inspiration

[Kun Chen - k-goku](https://github.com/kchen0x/k-goku)
[John Lindquist - dotfiles](https://github.com/johnlindquist/dotfiles)
[Nikita Voloboev - dotfiles](https://github.com/nikitavoloboev/dotfiles)
[Xah Lee - Banning the Shift Key](http://xahlee.info/kbd/banish_shift_key.html)
[Øystein Bech Gadmar - Colemak Forum - Extend Layer](https://forum.colemak.com/topic/2014-extend-extra-extreme/)


# Edit from here on

### Hyper Mode

Hyper mode is the way to take full use of CapsLock key. When `CapsLock` is pressed down, the hyper mode will be actived fot next action, and it will send `Escape` key when pressed alone.

#### Hyper Mode - Control

Hyper mode can be used as a `ctrl` key where it's mostly used in terminal for:

| key | effect                                      |
|-----|---------------------------------------------|
| `a` | tmux prefix                                 |
| `c` | kill a process with signal SIGINT           |
| `z` | suspend a process by sending it the SIGTSTP |
| `d` | `exit()` from the command                   |


### Misc

- Shift pressed alone to change input source
- Change right command to command-tab when used alone for jumping between two recent apps
- Change right option to 4 modifiers combination `⇧⌃⌥⌘`, and `f17` when used alone
- Quit apps by pressing command-q twice

## Installation

1. Install [Karabiner-Elements](https://pqrs.org/osx/karabiner/)
2. Create a profile in Karabiner-Elements which named 'Default'. (It will generate a karabiner.json file under ~/.config/karabiner/ folder for goku to use.)
3. Install [Goku](https://github.com/yqrashawn/GokuRakuJoudo)
4. Install files from this repo.

```
curl https://raw.githubusercontent.com/kiinoda/goku/master/karabiner.edn > ~/.config/karabiner.edn

goku
```