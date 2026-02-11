# `wmdot`

`wmdot` is yet another `git` wrapper to help keep tracking of dotfiles and more in the home directory.

It uses a bare git repository (by default at `~/.local/var/wmdot`) with `--git-dir` and `--work-tree` to track files throughout the home directory, without placing a `.git` folder in `$HOME`.

## Quick Start

### Debian/Ubuntu

```sh
# Install necessary tools, requires root
apt-get -y update
apt-get -y install curl git zsh tmux

# Clone wmdot-ex into the current home directory
sh -c "$(curl -fsSL https://go.keepconn.com/wmdot)" @ clone https://github.com/wmil/wmdot-ex.git

# Use zsh as the default shell
chsh -s `which zsh`
```

### macOS

```sh
# Install git if not already present
xcode-select --install

# Clone a home directory repository
sh -c "$(curl -fsSL https://go.keepconn.com/wmdot)" @ clone https://github.com/wmil/wmdot-ex.git
```

## Example

The repository https://github.com/wmil/wmdot-ex is an example home directory repository that can be used as a starting point.

## Commands

### Install Commands

| Command | Description |
|---------|-------------|
| `init` | Initialize a local repository |
| `clone <url>` | Clone an upstream repository into home directory |
| `cancel` | Remove all tracked files and the local repository |

### File Commands

| Command | Description |
|---------|-------------|
| `add` / `track` | Add files or changes into git index |
| `untrack` | Remove from git index but keep files |
| `co` / `checkout` | Restore tracked files from git index |
| `rm` | Untrack and remove files |
| `mv` | Move a tracked file |
| `au` / `add-update` | Stage modified tracked files |

### Repository Commands

| Command | Description |
|---------|-------------|
| `commit` | Commit changes to local repository |
| `push` | Push local committed changes to upstream |
| `pull` | Pull upstream and update submodules |
| `status` | Show status of tracked files |
| `diff` | Show diff of tracked files |
| `log` | Show commit logs |

### Submodule Commands

| Command | Description |
|---------|-------------|
| `sm-ls` | List all submodule directories |
| `sm-add <repo> <path>` | Add a submodule |
| `sm-del <path>...` | Delete submodules |
| `sm-update [path...]` | Update submodules from remote (all if no args) |
| `sm-reinit <path>...` | Deregister, re-register, re-initialize submodules |

### Extended Commands

| Command | Description |
|---------|-------------|
| `x <args>` | Execute raw git command with proper `--git-dir`/`--work-tree` |
| `ls` | List all tracked files |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `WMDOT_REPO` | `$HOME/.local/var/wmdot` | Path to the bare git repository |
| `WMDOT_ORIG` | `$HOME/.local/var/original` | Directory for backed-up original files during clone |
