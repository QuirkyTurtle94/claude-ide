# claude-ide

A tmux script that turns your terminal into a Claude-powered IDE with a 3-column layout:

```
┌──────────┬──────────────────┬──────────────┐
│          │                  │  terminal 1  │
│   yazi   │   Claude Code    ├──────────────┤
│  (~15%)  │    (~55%)        │  terminal 2  │
│          │                  │   (~30%)     │
└──────────┴──────────────────┴──────────────┘
```

- **Left**: [yazi](https://github.com/sxyazi/yazi) file browser
- **Center**: [Claude Code](https://github.com/anthropics/claude-code) (main pane)
- **Right**: Two shell panes for running commands

## Prerequisites

- [tmux](https://github.com/tmux/tmux)
- [Claude Code](https://github.com/anthropics/claude-code)
- [yazi](https://github.com/sxyazi/yazi)

### macOS (Homebrew)

```bash
brew install tmux yazi
npm install -g @anthropic-ai/claude-code
```

## Installation

Copy `claude-ide` to somewhere on your PATH and make it executable:

```bash
cp claude-ide ~/bin/claude-ide
chmod +x ~/bin/claude-ide
```

A reference `tmux.conf` is included with the recommended keybindings and navigation bar. Copy it or append to your existing config:

```bash
cp tmux.conf ~/.tmux.conf        # fresh install
cat tmux.conf >> ~/.tmux.conf    # append to existing
tmux source ~/.tmux.conf         # reload
```

## Usage

```bash
claude-ide              # uses current directory
claude-ide ~/my-project # specify a project directory
```

If a `claude-ide` tmux session already exists, it reattaches to it.

## Keybindings

| Key | Action |
|-----|--------|
| Alt+Arrow keys | Navigate between panes |
| Alt+z | Zoom/unzoom current pane |
| Prefix+d | Detach from session |
| q | Quit yazi |

## License

[MIT](LICENSE)
