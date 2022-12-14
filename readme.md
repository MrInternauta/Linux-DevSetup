# My Ubuntu config

## Development software

### zsh
<https://www.zsh.org/> 
```bash
# apt-get
sudo apt-get install zsh
```

type zsh
```bash
zsh
```

### oh-my-zsh
<https://ohmyz.sh/> 
```bash
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
### PowerLevel10k
<https://github.com/romkatv/powerlevel10k>
```bash
# gh cli
gh repo clone romkatv/powerlevel10k $ZSH_CUSTOM/themes/powerlevel10k

# git
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Then you need to enable it, change the value of ZSH_THEME to following in `~/.zshrc` file :
```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

### Configure Powerlevel10k Theme

Make sure your terminal font is FiraCode NF.
font link: <https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/FiraCode/Medium/complete/Fira%20Code%20Medium%20Nerd%20Font%20Complete.ttf>

for windows users: <https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/FiraCode/Medium/complete/Fira%20Code%20Medium%20Nerd%20Font%20Complete%20Windows%20Compatible.ttf>

type

```bash
p10k configure
```

### Plugins

- <https://github.com/zsh-users/zsh-autosuggestions> 
- <https://github.com/zsh-users/zsh-syntax-highlighting>
- <https://github.com/zsh-users/zsh-completions>
- <https://github.com/rajasegar/alacritty-themes>
- <https://gitmoji.dev/> 

### ls tools

- [color](https://github.com/athityakumar/colorls)
- [exa](https://the.exa.website/)

```bash
sudo apt install ruby-full
sudo gem install colorls

```

### secrets manager
- [secman](https://github.com/scmn-dev/secman): Human-friendly and amazing secrets manager.

```bash
# via npm
npm install -g secman

# via script
curl -fsSL https://cli.secman.dev | bash
```
### file transfer app
- [tran](https://github.com/abdfnx/tran): Securely transfer and send anything between computers with TUI.

```
curl -sL https://cutt.ly/tran-cli | bash
```

### Activate the plugins

In ~/.zshrc file replace the line starting with plugins=() to below line.

```bash
plugins=( git zsh-syntax-highlighting zsh-autosuggestions )
```

colors
```bash
if [ -x "$(command -v colorls)" ]; then
    alias ls="colorls"
    alias la="colorls -al"
fi
```

colors
```exa
if [ -x "$(command -v exa)" ]; then
    alias ls="exa"
    alias la="exa --long --all --group"
fi
```

after all these steps type
```bash
source ~/.zshrc
```

### Alacrity

<https://alacritty.org/> 

```yml
# Configuration for Alacritty, the GPU enhanced terminal emulator.

# Any items in the `env` entry below will be added as
# environment variables. Some entries may override variables
# set by alacritty itself.
env:
  # TERM variable
  #
  # This value is used to set the `$TERM` environment variable for
  # each instance of Alacritty. If it is not present, alacritty will
  # check the local terminfo database and use `alacritty` if it is
  # available, otherwise `xterm-256color` is used.
  TERM: alacritty
  LANG: "en_US.UTF-8"
  LC_CTYPE: en_US.UTF-8
window:
  # Window background opacity
  #
  # Specified in floating number from `0.0` to `1.0`.
  # The value `0.0` is completely transparent and `1.0` is opaque.
  opacity: 0.9
  # Window dimensions (changes require restart)
  #
  # Specified in number of columns/lines, not pixels.
  # If both are `0`, this setting is ignored.
  dimensions:
    columns: 90
    lines: 20
  # Window position (changes require restart)
  #
  # Specified in number of pixels.
  # If the position is not set, the window manager will handle the placement.
  #position:
  #  x: 0
  #  y: 0
  # Window padding (changes require restart)
  #
  # Blank space added around the window in pixels. This padding is scaled
  # by DPI and the specified value is always added at both opposing sides.
  padding:
    x: 0
    y: 0
  # Spread additional padding evenly around the terminal content.
  #dynamic_padding: false
  # Window decorations
  #
  # Values for `decorations`:
  #     - full: Borders and title bar
  #     - none: Neither borders nor title bar
  #
  # Values for `decorations` (macOS only):
  #     - transparent: Title bar, transparent background and title bar buttons
  #     - buttonless: Title bar, transparent background, but no title bar buttons
  #decorations: full
  # Startup Mode (changes require restart)
  #
  # Values for `startup_mode`:
  #   - Windowed
  #   - Maximized
  #   - Fullscreen
  #
  # Values for `startup_mode` (macOS only):
  #   - SimpleFullscreen
  startup_mode: Windowed
  # Window title
  title: Alacritty
  # Window class (Linux/BSD only):
  #class:
  # Application instance name
  #instance: Alacritty
  # General application class
  #general: Alacritty
  # GTK theme variant (Linux/BSD only)
  #
  # Override the variant of the GTK theme. Commonly supported values are `dark` and `light`.
  # Set this to `None` to use the default theme variant.
  #gtk_theme_variant: None
  #scrolling:
  # Maximum number of lines in the scrollback buffer.
  # Specifying '0' will disable scrolling.
  #history: 10000
  # Number of lines the viewport will move for every line scrolled when
  # scrollback is enabled (history > 0).
  #multiplier: 3

# Font configuration
font:
  # Normal (roman) font face
  normal:
    # Font family
    #
    # Default:
    #   - (macOS) Menlo
    #   - (Linux/BSD) monospace
    #   - (Windows) Consolas
    family: "Cascadia Code PL" #"FiraCode Nerd Font" "Cascadia Code PL" Monaco  monospace

    # The `style` can be specified to pick a specific face.
    style: Regular
    # Bold font face
    #bold:
    # Font family
    #
    # If the bold family is not specified, it will fall back to the
    # value specified for the normal font.
    #family: monospace
    # The `style` can be specified to pick a specific face.
    #style: Bold
    # Italic font face
    #italic:
    # Font family
    #
    # If the italic family is not specified, it will fall back to the
    # value specified for the normal font.
    #family: monospace
    # The `style` can be specified to pick a specific face.
    #style: Italic
    # Bold italic font face
    #bold_italic:
    # Font family
    #
    # If the bold italic family is not specified, it will fall back to the
    # value specified for the normal font.
    #family: monospace
    # The `style` can be specified to pick a specific face.
    #style: Bold Italic

  # Point size
  size: 11.0
  # Offset is the extra space around each character. `offset.y` can be thought of
  # as modifying the line spacing, and `offset.x` as modifying the letter spacing.
  #offset:
  #  x: 0
  #  y: 0
  # Glyph offset determines the locations of the glyphs within their cells with
  # the default being at the bottom. Increasing `x` moves the glyph to the right,
  # increasing `y` moves the glyph upwards.
  #glyph_offset:
  #  x: 0
  #  y: 0

# If `true`, bold text is drawn using the bright color variants.
#draw_bold_text_with_bright_colors: false
# Colors (Tomorrow Night Bright)
colors:
  # Default colors
  primary:
    background: '#282c34'
    foreground: '#abb2bf'

  # Normal colors
  normal:
    # NOTE: Use '#131613' for the `black` color if you'd like to see
    # black text on the background.
    black: '#282c34'
    red: '#e06c75'
    green: '#98c379'
    yellow: '#d19a66'
    blue: '#61afef'
    magenta: '#c678dd'
    cyan: '#56b6c2'
    white: '#abb2bf'

  # Bright colors
  bright:
    black: '#5c6370'
    red: '#e06c75'
    green: '#98c379'
    yellow: '#d19a66'
    blue: '#61afef'
    magenta: '#c678dd'
    cyan: '#56b6c2'
    white: '#ffffff'
theme: One-Dark
```
## Utility
Screenfetch
```bash
sudo apt install screenfetch
```
add screenfetch ~/.zshrc
### Configure Logitech MX Master 3 on Linux (LogiOps)
<https://danishshakeel.me/configure-logitech-mx-master-3-on-linux-logiops/>
https://volta.sh/
https://www.codegrepper.com/code-examples/shell/set+the+default+shell+to+zsh+in+alacritty
## Development
docker
java
volta
  angular
  typescript
  ionic
  express
  mongose
  gulp
  webpack
  nestjs


## Configuraciones Android DEveloper
```
~/.bashrc  ~/.zshrc ~/.bash_profile
____VARIABLES DE ENTORNO___
export ANDROID_SDK_ROOT=$HOME/Users/feliperamirez/Library/Android/sdk
```
### avdmanager, sdkmanager
```
export PATH=$PATH:$ANDROID_SDK_ROOT/tools/bin
export PATH=$PATH:$ANDROID_HOME/tools
```
### adb, logcat
```
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
```
### emulator
```
export PATH=$PATH:$ANDROID_SDK_ROOT/emulator
```
# JAVA
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_291.jdk/Contents/Home
export PATH=$PATH:$JAVA_HOME/bin

export PATH=$PATH:/Users/feliperamirez/gradle-7.1.1/bin
#BREW (HOME BREW)
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
#[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```