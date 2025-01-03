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
`brew install zsh zsh-autosuggestions zsh-syntax-highlighting`
`echo "source /usr/local/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc`
`echo "source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc`

* Install PowerLevel10k:
`brew install powerlevel10k`
`echo source '/usr/local/share/powerlevel10k/powerlevel10k.zsh-theme' >> ~/.zshrc`
`source ~/.zshrc`

	* Restart iterm2

## Basic Terminal Apps
`brew tap teamookla/speedtest`
`brew update && brew upgrade`                                                                                                                           
`brew install git python-tk gh speedtest`
`ln -s /usr/local/bin/python3.12 /usr/local/bin/python3`
`ln -s /usr/local/bin/python3 /usr/local/bin/python`

## SysAdmin Terminal Apps
`brew install swaks nmap mtr`

## Desktop Apps
`brew install --cask alt-tab google-chrome mounty balenaetcher maccy shottr keka numi logi-options+ mailspring tunnelblick`
`brew install --cask betterdisplay apache-directory-studio bitwarden caffeine deepl disk-inventory-x drawio box-drive inssider keka mark-text novabench rectangle resolutionator rustdesk vlc warp xca`

## Coding Apps
`brew install --cask sublime-text github visual-studio-code macdown modern-csv`

## Remote Control Apps
`brew install --cask royal-tsx windows-app rustdesk`

## Hackintosh Apps
`brew install --cask hackintool karabiner-elements`

## Hackintosh Tools
* ProperTree: `gh repo clone corpnewt/ProperTree`
* GenSMBIOS: `gh repo clone corpnewt/GenSMBIOS`
* OC-Update: `gh repo clone corpnewt/OC-Update`
* OCupdater: `gh repo clone Lovely-XPP/OCUpdater`
* octool: `gh repo clone rusty-bits/octool`
* gibMacOS: `gh repo clone corpnewt/gibMacOS`

## Other Tools
* MenuPing: https://github.com/julienbordet/MenuPing/releases/latest
* JsonEditor: https://github.com/jxo-me/JsonEditor/releases/latest
