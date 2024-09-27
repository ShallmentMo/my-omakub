# MY MACOS SUPPORT

## Mac Default

```bash
# Enable tap-to-click for the trackpad and show the correct state in System Preferences
defaults write com.apple.AppleMultitouchTrackpad Clicking -bool true
defaults -currentHost write -g com.apple.mouse.tapBehavior -int 1

# Disable the .DS file creation
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true
defaults write com.apple.desktopservices DSDontWriteUSBStores -bool true

# Show the path bar in the Finder
defaults write com.apple.finder "ShowPathbar" -bool "true" && killall Finder

# Show hidden files in the Finder
defaults write com.apple.finder "AppleShowAllFiles" -bool "false" && killall Finder

# Keep folders on top in Finder
defaults write com.apple.finder "_FXSortFoldersFirst" -bool "true" && killall Finder

# Keep folders on top on Desktop
defaults write com.apple.finder "_FXSortFoldersFirstOnDesktop" -bool "true" && killall Finder

# Apply the settings
/System/Library/PrivateFrameworks/SystemAdministration.framework/Resources/activateSettings -u
```

## Install [Homebrew](https://brew.sh/)

### Install using Brewfile

```bash
# download Brewfile first
brew bundle --file path/to/Brewfile
```

## upgrade bash

```bash
bash --version
echo "$(brew --prefix)/bin/bash" | sudo tee -a /private/etc/shells
sudo chpass -s /usr/local/bin/bash roger
```

## install git

```bash
# 使用 bash-completion@2, 因为 bash-completion 只支持旧版 bash
brew install git bash-completion@2
```

## install bin

```bash
brew install mise
# fastfetch 可有可无，如果需要安装，请使用 brew 安装
# brew install fastfetch
brew install gh
brew install git-extras
# 可以用 docker desktop
# brew install lazydocker
# brew install lazygit
# omakub 使用 lazygit 的，但是我一般用 tig
brew install tig
# 现在用 cursor
# brew install neovim
brew install zellij
brew install fzf
brew install ripgrep
brew install bat
brew install eza
brew install zoxide
brew install btop
brew install fd
brew install tldr
# select storage sh need gum
brew install gum
# gitlab cli
brew install glab
# 纯属个人推荐使用, 其他人辩证使用
# brew install you-get
# curl --proto '=https' --tlsv1.2 -LsSf https://setup.atuin.sh | sh
# brew install blueutil
```

### using cargo-binstall

You can install mise first and then use mise to install rust and cargo-binstall. But if you use cargo-binstall, you might have to fix up your bash env.

```bash
cargo binstall rainfrog
```

## install [oh-my-bash](https://github.com/ohmybash/oh-my-bash)

## clone my omakub

```
git clone https://github.com/ShallmentMo/my-omakub.git
git checkout my-stable
```

## run commands

```bash
cp ~/.bash_profile ~/.bash_profile.bak
cp ~/.local/share/omakub/configs/bash_profile ~/.bash_profile
cp ~/.bashrc ~/.bashrc.bak
cp ~/.local/share/omakub/configs/bashrc ~/.bashrc
source ~/.local/share/omakub/defaults/bash/shell
cp ~/.local/share/omakub/configs/inputrc ~/.inputrc
```

## install Docker Desktop

```bash
brew install --cask docker
```

## install apple container

```bash
brew install container
```

config docker desktop proxies

## install database

### Using Docker

```bash
bash ~/.local/share/omakub/install/terminal/select-dev-storage.sh
```

### Using container

```bash
container run --name postgres17 -d -p 5432:5432 --env POSTGRES_HOST_AUTH_METHOD=trust docker.io/library/postgres:17.4-alpine
container run --name redis7 -d -p 6379:6379 docker.io/library/redis:7-alpine
```

## set git

```bash
bash ~/.local/share/omakub/install/terminal/set-git.sh
```

## install apps

```bash
brew install --cask alacritty
brew install --cask google-chrome
brew install --cask brave-browser
# brew install --cask flameshot
brew instlal --cask vlc
brew instlal --cask cursor
brew instlal --cask visual-studio-code
brew instlal --cask enpass
```

## font

omakub use cascadia, but I prefer monaspace

```bash
brew install font-monaspace
brew install font-monaspace-nerd-font
```

## copy config

```bash
mkdir -p ~/.config/alacritty
cp ~/.local/share/omakub/configs/alacritty.toml ~/.config/alacritty/alacritty.toml
cp ~/.local/share/omakub/themes/tokyo-night/alacritty.toml ~/.config/alacritty/theme.toml
cp ~/.local/share/omakub/configs/alacritty/fonts/Monaspace.toml ~/.config/alacritty/font.toml
cp ~/.local/share/omakub/configs/alacritty/font-size.toml ~/.config/alacritty/font-size.toml
mkdir -p ~/.config/zellij
cp ~/.local/share/omakub/configs/zellij.kdl ~/.config/zellij/config.kdl
mkdir -p ~/.config/zellij/themes
cp ~/.local/share/omakub/themes/tokyo-night/zellij.kdl ~/.config/zellij/themes/tokyo-night.kdl
mkdir -p ~/.config/zellij/layouts
cp ~/.local/share/omakub/themes/tokyo-night/zellij-layouts/my.kdl ~/.config/zellij/layouts/my.kdl
cp ~/.local/share/omakub/themes/tokyo-night/zellij-layouts/my.swap.kdl ~/.config/zellij/layouts/my.swap.kdl
```
