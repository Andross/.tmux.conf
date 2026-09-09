# .tmux.conf

My tmux config: truecolor, vi-style copy mode, and a Catppuccin Mocha status
bar managed by TPM.

## Install

tmux checks both locations, so either works:

```sh
# home root
curl -fsSL https://raw.githubusercontent.com/Andross/.tmux.conf/main/.tmux.conf \
  -o ~/.tmux.conf

# or XDG
mkdir -p ~/.config/tmux
curl -fsSL https://raw.githubusercontent.com/Andross/.tmux.conf/main/.tmux.conf \
  -o ~/.config/tmux/tmux.conf
```

Then start tmux. TPM clones itself in the background on first run and the theme
applies a few seconds later — no manual install step, and a slow or stalled
clone will not hold up startup.

## Copy mode

vi-style. `prefix` is the default `C-b`.

| key | action |
| --- | --- |
| `prefix + [` | enter copy mode |
| `Space` | begin selection |
| `Enter` | copy and exit |
| `v` | toggle rectangle select |
| `V` | select line |
| `q` | cancel |

## Settings

- `tmux-256color` plus RGB `terminal-overrides` — truecolor
- `focus-events on` — nvim `autoread` and `FocusGained` autocmds fire
- `escape-time 0` — no Esc lag in nvim
- `mouse on`, 1-based window and pane indexes, `renumber-windows on`
- `display-time 4000` — messages stay readable
- `history-limit 10000`

## Plugins

Managed by [TPM](https://github.com/tmux-plugins/tpm). `TMUX_PLUGIN_MANAGER_PATH`
is pinned so plugins always install to `~/.config/tmux/plugins/`, regardless of
which of the two config locations this file lives in.

- [catppuccin/tmux](https://github.com/catppuccin/tmux) `v2.3.0` — Mocha flavor,
  rounded window status, with session / uptime / date-time modules

`prefix + I` to install · `prefix + U` to update
