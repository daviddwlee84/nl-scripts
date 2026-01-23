# Setup UNIX development environments

Please make sure the following tools are setup properly

- Oh-my-zsh + Nerd Fonts
  - `sudo apt install zsh` (if zsh not exist)
  - `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
- git (zsh git plugins)+ LazyGit
- NeoVim + LazyVim (sync plugins)
- fzf + setup zsh autocompletion (`zsh-autosuggestions`, `zsh-syntax-highlighting` plugins)
  - `cd ~/.oh-my-zsh/custom/plugins`
  - `git clone https://github.com/zsh-users/zsh-autosuggestions.git`
  - `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git`
- Docker
  - `curl -fsSL https://get.docker.com -o get-docker.sh`, `sudo sh get-docker.sh`: <https://docs.docker.com/engine/install/ubuntu/>
  - <https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user>
- Install Pueue <https://github.com/Nukesor/pueue> and make sure the pueued is setup

## MacOS

> use launchd replace systemd

Setup Homebrew

---

Tmux

<https://github.com/tmux-plugins/tpm>

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

`~/.tmux.conf`

```conf
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'github_username/plugin_name#branch'
# set -g @plugin 'git@github.com:user/plugin'
# set -g @plugin 'git@bitbucket.com:user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

```bash
# type this in terminal if tmux is already running
tmux source ~/.tmux.conf
```

<https://gist.github.com/matej-g/8327407d945247da6e0ac7bec8a0a51e>

```conf
setw -g mouse on
setw -g mode-keys vi
```

Theme

<https://draculatheme.com/tmux>
<https://github.com/wfxr/tmux-power>
