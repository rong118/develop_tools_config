## Setup zsh

- Set zsh as default shell (Current MacOS uses zsh as default):
  
  ```
  $ chsh -s /bin/zsh
  ```

- Install Oh My Zsh

  ```
  $ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
  ```

- Open zshrc file and change theme

  ```
  vim ~/.zshrc
  ```

  Use ZSH_THEME="agnoster" as theme.

- Download font

  Meslo font: https://github.com/powerline/fonts/blob/master/Meslo%20Slashed/Meslo%20LG%20M%20Regular%20for%20Powerline.ttf

  (TODO) needs to use fonts with lunarvim(nvimtree)

- zsh-syntax-highlighting
    
  ```
  $ brew install zsh-syntax-highlighting
  ```

  Appends below line at the end of zshrc
  ```
  source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
  ```

- auto suggestion

  ```
  git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
  ```

- Finish with others setup

## My zshrc config
- [zshrc](https://github.com/rong118/develop_tools_config/blob/master/iterm2_setup/zshrc)
