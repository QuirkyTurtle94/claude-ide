# claude-ide

A tmux script that turns your terminal into a Claude-powered IDE with a 3-column layout:

```
┌──────────┬──────────────────┬──────────────┐
│          │                  │   lazygit    │
│   yazi   │   Claude Code    ├──────────────┤
│  (~15%)  │    (~55%)        │   terminal   │
│          │                  │   (~30%)     │
└──────────┴──────────────────┴──────────────┘
```

- **Left**: [yazi](https://github.com/sxyazi/yazi) file browser
- **Center**: [Claude Code](https://github.com/anthropics/claude-code) (main pane)
- **Right top**: [lazygit](https://github.com/jesseduffield/lazygit) for git management
- **Right bottom**: Shell for running commands

## Prerequisites

- [tmux](https://github.com/tmux/tmux)
- [Claude Code](https://github.com/anthropics/claude-code)
- [yazi](https://github.com/sxyazi/yazi)
- [lazygit](https://github.com/jesseduffield/lazygit)

### macOS (Homebrew)

```bash
brew install tmux yazi lazygit
npm install -g @anthropic-ai/claude-code
```

## Installation

Copy `claude-ide` to somewhere on your PATH and make it executable:

```bash
cp claude-ide ~/bin/claude-ide
chmod +x ~/bin/claude-ide
```

## Usage

```bash
claude-ide              # uses current directory
claude-ide ~/my-project # specify a project directory
```

If a `claude-ide` tmux session already exists, it reattaches to it.

## Recommended tmux keybindings

Add these to your `~/.tmux.conf` for easy pane navigation:

```tmux
# Pane navigation (Alt+Arrow, no prefix needed)
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

# Zoom toggle (Alt+z)
bind -n M-z resize-pane -Z
```

## License

[MIT](LICENSE)
