# phyhui dotfiles

**Warning**: Don’t blindly use my settings unless you know what they are doing (:

## Contents

- neovim config
- tmux config
- [fish config](#fish-shell-config)
- PowerShell config

## Fish Shell Config
### Sources
- [Fish shell](https://fishshell.com/) - actual shell
- [Fisher](https://github.com/jorgebucaran/fisher) - Plugin manager
- [Tide](https://github.com/IlanCosman/tide) - Shell theme. Use version 5: `fisher install ilancosman/tide@v5`
- [Nerd fonts](https://github.com/ryanoasis/nerd-fonts) - Powerline-patched fonts. I use Hack Nerd Font.
- [z for fish](https://github.com/jethrokuan/z) - Directory jumping
- [Exa](https://the.exa.website/) - `ls` replacement
- [ghq](https://github.com/x-motemen/ghq) - Local Git repository organizer
- [fzf](https://github.com/junegunn/fzf) - fuzzy finder
- [ghq for fish](https://github.com/decors/fish-ghq) -  completions and keybindings for ghq
- [fzf for fish](https://github.com/jethrokuan/fzf) - fzf integration for fish

### Installation Guide
#### windows
1. Enable WSL and install Ubuntu from Microsoft Store (Windows only)
2. If you install Homebrew with WSL it will be in a custom directory with all the apps you install with brew.
You will have to make brew and all the apps globally available with this command: `eval (/home/linuxbrew/.linuxbrew/bin/brew shellenv)`. Put this in your `config.fish` (if you use mine its already included)
3. Install fish shell. Example: `brew install fish`.
4. Add it to your the "shells" directory with `echo $(which fish) | sudo tee -a /etc/shells`
5. Make it your default shell with `chsh -s $(which fish)` in bash.
#### macos
1. Install fish: `brew install fish`
2. Start fish: `fish`
3. Add brew to your fish path: `fish_add_path /opt/homebrew/bin`
4. Add fish shell to your shells: `echo "/opt/homebrew/bin/fish" | sudo tee -a /etc/shells`
5. Make fish your default shell: `chsh -s /opt/homebrew/bin/fish`
#### all systems
6. Install Nerd Fonts directly from website on your system and set it in your terminal application.
7. Install Fisher as plugin manager. `curl -sL https://git.io/fisher | source && fisher install jorgebucaran/fisher`
8. Install Tide theme with Fisher. `fisher install ilancosman/tide@v5`
9. After configuring tide, copy parameters from `conf.d/tide.fish` to the end of `conf.d/_tide_init.fish` file.
10. Install z for fish. `fisher install jethrokuan/z`
11. Install exa. `apt install exa` or `brew install exa`

If its not availabe, download it manually:
```md
wget -c http://old-releases.ubuntu.com/ubuntu/pool/universe/r/rust-exa/exa_0.9.0-4_amd64.deb
sudo apt-get install ./exa_0.9.0-4_amd64.deb
```
12. Install ghq  `brew install ghq`
13.  Install fzf `brew install fzf`
14.  Install ghq for fish `fisher install decors/fish-ghq`
15.  Install fzf for fish `fisher install jethrokuan/fzf`
16.  Put fish config files in `home/user/.config/fish` folder

### Usage
#### Fish shell
- Just a better Shell lol

#### Fisher
- install packages: `fisher install githubname/repo`
- uninstall packages: `fisher remove githubname/repo`
- list installed packages: `fisher list`

#### Tide
- configuration: `tide configure`

#### Nerd Font
- Just better fonts, idk

#### z for fish
- Used for directory jumping.
- Remembers which diretories you visited and you can instantly jump to them without having to type the whole path
- Example: `z desk` to jump to desktop or `z dotfiles` and you will end up in the dotfiles github repo

#### exa

- Just makes `ll` look better

#### ghq and fzf

- Shortcuts

|   Keybindings   | Remarks                                         |
| --------------- | ----------------------------------------------- |
| Ctrl-o          | Find a file.                                    |
| Ctrl-r          | Search through command history.                 |
| Alt-c           | cd into sub-directories (recursively searched). |
| Alt-Shift-c     | cd into sub-directories, including hidden ones. |
| Alt-o           | Open a file/dir using default editor ($EDITOR)  |
| Alt-Shift-o     | Open a file/dir using xdg-open or open command  |

- [tutorial website](https://fotoallerlei.com/blog/post/2019/ghq/post/)
