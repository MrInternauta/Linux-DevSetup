# My Ubuntu config

## Development software

### zsh
<https://www.zsh.org/> 
```bash
# apt-get
sudo apt-get install zsh
sudo apt install curl
```

type
```bash
zsh
```
### Set ZSH as default 
-  <https://www.codegrepper.com/code-examples/shell/set+the+default+shell+to+zsh+in+alacritty>
- `chsh -s /bin/zsh`

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
<[https://github.com/tonsky/FiraCode/releases](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode)>
type

```bash
p10k configure
```

### Plugins

- <https://github.com/zsh-users/zsh-autosuggestions> 
- <https://github.com/zsh-users/zsh-syntax-highlighting>
- <https://github.com/zsh-users/zsh-completions>

### Activate the plugins

In ~/.zshrc file replace the line starting with plugins=() to below line.

```bash
plugins=( git zsh-syntax-highlighting zsh-autosuggestions )
```

### ls tools
- [color](https://github.com/athityakumar/colorls)
- [exa](https://the.exa.website/)

```bash
sudo apt install ruby-full
sudo gem install colorls

```
#### for colors
Add to `~/.zshrc`
```bash
if [ -x "$(command -v colorls)" ]; then
    alias ls="colorls"
    alias la="colorls -al"
fi
```
#### for exa
```exa
if [ -x "$(command -v exa)" ]; then
    alias ls="exa"
    alias la="exa --long --all --group"
fi
```

### Utility
Screenfetch
```bash
sudo apt install screenfetch
```
add screenfetch `~/.zshrc`

## Alacrity
<https://alacritty.org/> 

- Install the Rust compiler with rustup rustup.rs <https://rustup.rs>

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
- To make sure you have the right Rust compiler installed, run
```bash
rustup override set stable
rustup update stable
```
- Dependencies: Debian/Ubuntu
-  -If you'd like to build a local version manually, you need a few extra libraries to build Alacritty. Here's an apt command that should install all of them. If something is still found to be missing, please open an issue. 
```bash
sudo apt-get install cmake pkg-config libfreetype6-dev libfontconfig1-dev libxcb-xfixes0-dev libxkbcommon-dev python3
```
- Install with cargo
```bash
cargo install alacritty
```

- Clone
```bash
git clone https://github.com/alacritty/alacritty.git
cd alacritty
```
- Build
```bash
# Force support for only Wayland
cargo build --release --no-default-features --features=wayland

# Force support for only X11
cargo build --release --no-default-features --features=x11
```

- Post Build
Terminfo: To make sure Alacritty works correctly, either the alacritty or alacritty-direct terminfo must be used. The alacritty terminfo will be picked up automatically if it is installed.
If the following command returns without any errors, the alacritty terminfo is already installed:
```bash
infocmp alacritty
```

If it is not present already, you can install it globally with the following command:
``` bash
sudo tic -xe alacritty,alacritty-direct extra/alacritty.info
```
### Desktop Entry
Many Linux and BSD distributions support desktop entries for adding applications to system menus. This will install the desktop entry for Alacritty:
```
sudo cp target/release/alacritty /usr/local/bin # or anywhere else in $PATH
sudo cp extra/logo/alacritty-term.svg /usr/share/pixmaps/Alacritty.svg
sudo desktop-file-install extra/linux/Alacritty.desktop
sudo update-desktop-database
```

## Development

### Install Volta | The Hassle-Free JavaScript Tool Manager
- https://volta.sh/
```bash
# install Volta
curl https://get.volta.sh | bash

# install Node
volta install node

# start using Node
node
```
### 🌈 alacritty-themes 🍭
- <https://github.com/rajasegar/alacritty-themes>

### gitmoji
- <https://gitmoji.dev/> 

    
### docker
    <https://www.docker.com/>
### angular
    <https://angular.io/cli>
    ```bash
    npm install -g @angular/cli
    ```

### typescript
    <https://www.typescriptlang.org/docs/>
    ```bash
    #Dev
    npm install typescript --save-dev
    #Global
    npm install typescript -g
    #compile
    npx tsc
    ```
### ionic
<https://ionicframework.com/>
```
npm i -g @ionic/cli
```
### gulp
<https://gulpjs.com/docs/en/getting-started/quick-start/>
```
npm install --global gulp-cli
npm install --save-dev gulp
```
### webpack
<https://webpack.js.org/>
```bash
Install with npm:
npm install --save-dev webpack
Install with yarn:

yarn add webpack --dev

```
### Nestjs
<https://nestjs.com/>
```
npm i -g @nestjs/cli
nest new project-name
```

### Configure Logitech MX Master 3 on Linux (LogiOps)
<https://danishshakeel.me/configure-logitech-mx-master-3-on-linux-logiops/>



### Set JDK, maven, gradle and JRE - SDKMNAN
    <[https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-20-04-es](https://sdkman.io/install)>
- sdk install java 23.ea.17-open
- sdk install maven
- sdk install gradle
    
## Configuraciones Android DEveloper
<https://developer.android.com/studio

```
sudo snap install android-studio --classic
```

## Variable environments
```
~/.zshrc 
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

### Generate ssh and connect Github

```
 ssh-keygen -t rsa -b 4096 -C "feldjesus@gmail.com"

```


## After all these steps type
```bash
source ~/.zshrc
```
