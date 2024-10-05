# Post Installation Steps
## Custom Settings
* Disable Gatekeeper: `sudo spctl --master-disable`

* Disable sudo password prompt: `sudo visudo`
> %admin          ALL = (ALL) NOPASSWD:ALL

* Install brew: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
 

## Terminal
* Install iTerm: `brew install --cask iterm2`

* Install Oh My Zsh:
`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
`brew install zsh zsh-completions zsh-autosuggestions` 

* Install PowerLevel10k:
`brew install powerlevel10k`
`echo source '/usr/local/share/powerlevel10k/powerlevel10k.zsh-theme' >> ~/.zshrc`
`source ~/.zshrc`

	* Restart iterm2

## Basic Terminal Apps
`brew tap teamookla/speedtest`
`brew update && brew upgrade`                                                                                                                           
`brew install git python-tk gh speedtest`

## Desktop Apps
`brew install --cask alt-tab google-chrome mounty balenaetcher maccy shottr keka numi`

## Coding Apps
`brew install --cask sublime-text github vscode macdown`

## Hackintosh Apps
`brew install --cask hackintool karabiner-elements`

