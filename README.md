# Gabe's dotfiles

This repo contains the [dotfiles](https://dotfiles.github.io/) to configure Gabe's preferred Linux environment. It is assumed that [zsh](https://www.zsh.org/) and [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh/) are installed before applying these dotfiles using [chezmoi](https://www.chezmoi.io/).

The following shell customizations are defined:
- Oh-my-zsh theme: [Powerlevel10k](https://github.com/romkatv/powerlevel10k)
  - Prompt style: Rainbow
  - Character set: Unicode
  - Show current time: No
  - Prompt separators: Angled
  - Prompt heads: Sharp
  - Prompt tails: Flat
  - Prompt height: One line
  - Prompt spacing: Compact
  - Prompt flow: Concise
  - Enable Transient Prompt: No
- Oh-my-zsh plugins:
  - [gitfast](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/gitfast): Autocompletion and aliases for git
  - [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions): Grey prompt completion suggestions
  - [colored-man-pages](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/colored-man-pages): Color highlighting for manual pages
  - [command-not-found](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/command-not-found): Gives suggestions when a command is not found

## Installation

### Install zsh and oh-my-zsh

```bash
# Install zsh.
sudo apt-get update && sudo apt-get install --yes zsh

# Set default shell to zsh.
sudo chsh $USER -s $(which zsh)

# Install oh-my-zsh.
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Install chezmoi and apply dotfiles

```bash
# Install chezmoi and apply dotfiles from this repo.
sh -c "$(curl -fsLS chezmoi.io/get)" -- -b ~/.local/bin init --apply gabe-microsoft
```

### Install in VS Code Development Container or Codespaces

Use the following settings:

```json
{
  "dotfiles.repository": "gabe-microsoft/dotfiles",
  "dotfiles.targetPath": "~/dotfiles",
  "dotfiles.installCommand": "~/dotfiles/install.sh"
}
```

For details, see [Personalizing dev containers](https://code.visualstudio.com/docs/remote/containers#_personalizing-with-dotfile-repositories) and [chezmoi with containers](https://www.chezmoi.io/user-guide/machines/containers-and-vms/).
