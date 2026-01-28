# UNIX Development Environment Setup

Make sure the following tools are properly installed and configured. Detect the current OS (Ubuntu/Debian or MacOS) and use the appropriate installation method.

On MacOS, install Homebrew first if not already present, then prefer `brew install` for most tools.

## Package Manager (MacOS)

- Homebrew: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

## Shell: Zsh + Oh-My-Zsh

> If user has already some custom config in `~/.bashrc`, try to bring them to `~/.zshrc`

- Install zsh if not present
  - Ubuntu: `sudo apt install zsh`
  - MacOS: pre-installed
- Set zsh as default shell: `chsh -s $(which zsh)`
- Install Oh-My-Zsh: `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
- Install plugins:
  - `git clone https://github.com/zsh-users/zsh-autosuggestions.git ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions`
  - `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting`
- Configure `~/.zshrc` plugins: `plugins=(git zsh-autosuggestions zsh-syntax-highlighting fzf)`

## Nerd Fonts

Required for terminal icons in LazyVim, Powerlevel10k, etc.

- MacOS: `brew install --cask font-jetbrains-mono-nerd-font` (or another Nerd Font of choice)
- Ubuntu: download from <https://github.com/ryanoasis/nerd-fonts/releases> and install to `~/.local/share/fonts/`, then run `fc-cache -fv`
- Configure your terminal emulator to use the installed Nerd Font

## Git + LazyGit

- git
  - Ubuntu: `sudo apt install git`
  - MacOS: `brew install git`
- LazyGit: <https://github.com/jesseduffield/lazygit>
  - Ubuntu: download binary from GitHub releases or use the official PPA
  - MacOS: `brew install lazygit`

## fzf (Fuzzy Finder)

- Ubuntu: `sudo apt install fzf` or install from git: `git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf && ~/.fzf/install`
- MacOS: `brew install fzf && $(brew --prefix)/opt/fzf/install`

## NeoVim + LazyVim

- NeoVim: <https://github.com/neovim/neovim>
  - Ubuntu: download the latest stable appimage or build from source (the apt version is often outdated)
  - MacOS: `brew install neovim`
- LazyVim: <https://www.lazyvim.org/installation>
  - Back up existing config: `mv ~/.config/nvim ~/.config/nvim.bak`
  - Clone starter: `git clone https://github.com/LazyVim/starter ~/.config/nvim && rm -rf ~/.config/nvim/.git`
  - Launch `nvim` to sync plugins

## Tmux + TPM

- Install tmux
  - Ubuntu: `sudo apt install tmux`
  - MacOS: `brew install tmux`
- Install TPM (Tmux Plugin Manager): `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`
- Create/update `~/.tmux.conf`:

```conf
setw -g mouse on
setw -g mode-keys vi

# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

- Reload config if tmux is running: `tmux source ~/.tmux.conf`
- Install plugins: press `prefix + I` inside tmux

## Docker

- Ubuntu:
  - `curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh`
  - Add user to docker group (rootless): `sudo usermod -aG docker $USER && newgrp docker`
  - Reference: <https://docs.docker.com/engine/install/ubuntu/>
- MacOS: `brew install --cask docker` (Docker Desktop) or `brew install docker` (CLI only)

## Pueue (Task Queue Manager)

<https://github.com/Nukesor/pueue>

- Ubuntu: download binary from GitHub releases or `cargo install pueue`
- MacOS: `brew install pueue`
- Start the daemon: `pueued -d`
- To auto-start on boot:
  - Ubuntu (systemd): `systemctl --user enable --now pueued`
  - MacOS (launchd): `brew services start pueue`
