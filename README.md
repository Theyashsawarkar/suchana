# suchana

**suchana** (सूचना, "notice") — Notifications. A tool for [Vyom](https://github.com/Theyashsawarkar/vyom), the keyboard-driven panels of [Vayu](https://github.com/Theyashsawarkar/vayu); in Vayu it replaces notification-history.py.

> Notifications (mako): what's on screen with its actions, the history grouped by app, a full preview, do not disturb.

## Features

- What's **on screen now**, with the actions it offers (run them, or dismiss it).
- The history, **grouped by app**, newest first, with each app's icon; urgent ones flagged.
- The preview shows the whole message.
- A **do not disturb** switch (mako's `do-not-disturb` mode, or your own commands).

## Keys

| Key | Action |
|---|---|
| `Enter` | Run the notification's default action, or copy its text |
| `Ctrl+C` | Copy the notification's text |
| `Ctrl+Backspace` | Dismiss the on-screen notification |
| `Ctrl+N` | Turn do not disturb on or off |
| `Esc` | close |

Every Vyom panel also has: `Up`/`Down` (or `Ctrl+K`/`Ctrl+J`) to move, `Page Up`/`Page Down`, `Tab` to switch to the next tool.

## Requirements

- [Vyom](https://github.com/Theyashsawarkar/vyom) 0.2 or newer (Python 3.11+, GTK 4, gtk4-layer-shell, a layer-shell compositor)
- `makoctl`

## Install

```sh
git clone https://github.com/Theyashsawarkar/suchana ~/.local/share/vyom/plugins/suchana
vyom reload        # or log out and in
vyom suchana         # open it (again: close it)
```

Bind it to a key, e.g. in sway:

```
bindsym $mod+<key> exec vyom suchana
```

Update: `git -C ~/.local/share/vyom/plugins/suchana pull && vyom reload`. `vyom list` shows every installed tool and why one would be skipped.

## Configuration

In `~/.config/vyom/config.toml` (all optional):

```toml
[plugin.suchana]
# dnd_status: command printing the current mode (default: (makoctl mode))
# dnd_on_when: regex: do not disturb is on (default: ^dnd$)
# dnd_on / dnd_off: commands to turn it on / off (default: (makoctl mode -a/-r))
```

## License

MIT.
