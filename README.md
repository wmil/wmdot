# `wmdot`

`wmdot` is yet another `git` wrapper to help keep tracking of dotfiles and more in the home directory.

## Example

The repository https://github.com/wmil/wmdot-ex is an example home directory repository.

It can be cloned into your own home directory with the following commands, assuming a fresh Debian installation:

```
# Install necessary tools, requires root
apt-get -y update
apt-get -y install curl git zsh

# Clone wmdot-ex into the current home directory
sh -c "$(curl -fsSL https://go.keepconn.com/wmdot)" @ clone https://github.com/wmil/wmdot-ex.git

# Use zsh as the default shell
chsh -s `which zsh`
```
