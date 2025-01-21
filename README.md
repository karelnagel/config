# command line tools + git
git 
then popup asks to install the tools

# brew 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# brave 
brew install --cask brave-browser

# set brave as default browser
open -a "Brave Browser" --args --make-default-browser


# bitwarden
brew install --cask bitwarden

# rectangle 
brew install --cask rectangle

# logitech options 
brew install --cask logi-options+

# vscode 
brew install --cask visual-studio-code

# vscode settings.json
# Download vscode settings
curl -o ~/Library/Application\ Support/Code/User/settings.json https://raw.githubusercontent.com/karelnagel/config/refs/heads/main/settings.json


# vscode extensions
astro, deno,file-size, git graph, go, jupyter, markdown, prettier, sqlite viewer


# nvm 
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
nvm install --lts 
nvm use --lts

# deno 
curl -fsSL https://deno.land/install.sh | sh

# karabiner
brew install --cask karabiner-elements

# Download karabiner config
curl -o ~/.config/karabiner/karabiner.json https://raw.githubusercontent.com/karelnagel/config/refs/heads/main/karabiner.json



# new ssh key
ssh-keygen
cat ~/.ssh/id_rsa.pub

# cloudflared 
brew install cloudflared
add host + then add remote ssh:localhost:22
then you can connect with

Host user.domain.com
  User user
  ProxyCommand cloudflared access ssh --hostname %h


# enable ssh access
sudo systemsetup -setremotelogin on


# UI settings
# Disable window animations
defaults write NSGlobalDomain NSAutomaticWindowAnimationsEnabled -bool false

# Disable animations when opening and closing windows
defaults write NSGlobalDomain NSWindowResizeTime -float 0.001

# Disable animations when opening a Quick Look window
defaults write -g QLPanelAnimationDuration -float 0

# Disable animation when opening the Info window in Finder
defaults write com.apple.finder DisableAllAnimations -bool true

# Disable animations when opening applications
defaults write com.apple.dock launchanim -bool false

# Disable the "Are you sure you want to open this application?" dialog
defaults write com.apple.LaunchServices LSQuarantine -bool false

# Show all file extensions
defaults write NSGlobalDomain AppleShowAllExtensions -bool true

# Disable auto-correct
defaults write NSGlobalDomain NSAutomaticSpellingCorrectionEnabled -bool false

# Disable auto-capitalization
defaults write NSGlobalDomain NSAutomaticCapitalizationEnabled -bool false

# Disable smart quotes and dashes
defaults write NSGlobalDomain NSAutomaticQuoteSubstitutionEnabled -bool false
defaults write NSGlobalDomain NSAutomaticDashSubstitutionEnabled -bool false

# Disable press-and-hold for keys in favor of key repeat
defaults write NSGlobalDomain ApplePressAndHoldEnabled -bool false

defaults write -g InitialKeyRepeat -int 13
defaults write -g KeyRepeat -int 1.4

# Keep only essential dock items (Brave, VS Code, Terminal)
defaults write com.apple.dock persistent-apps -array \
  '<dict><key>tile-data</key><dict><key>file-data</key><dict><key>_CFURLString</key><string>/Applications/Brave Browser.app</string><key>_CFURLStringType</key><integer>0</integer></dict></dict></dict>' \
  '<dict><key>tile-data</key><dict><key>file-data</key><dict><key>_CFURLString</key><string>/Applications/Visual Studio Code.app</string><key>_CFURLStringType</key><integer>0</integer></dict></dict></dict>' \
  '<dict><key>tile-data</key><dict><key>file-data</key><dict><key>_CFURLString</key><string>/System/Applications/Utilities/Terminal.app</string><key>_CFURLStringType</key><integer>0</integer></dict></dict></dict>'
defaults write com.apple.dock persistent-others -array
defaults write com.apple.dock tilesize -int 36
killall Dock

# Make dock small and auto-hide
defaults write com.apple.dock autohide -bool true
defaults write com.apple.dock autohide-delay -float 0
defaults write com.apple.dock autohide-time-modifier -float 0.5
defaults write com.apple.dock tilesize -int 30
killall Dock

# Disable Mac startup sound
sudo nvram SystemAudioVolume=" "
sudo nvram StartupMute=%01

# Enable secondary click (right-click) with two fingers
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad TrackpadRightClick -bool true
defaults write com.apple.AppleMultitouchTrackpad TrackpadRightClick -bool true
defaults write NSGlobalDomain com.apple.trackpad.enableSecondaryClick -bool true

# install alt tab
brew install --cask alt-tab
