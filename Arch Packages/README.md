# How to install some packages

> notes from 2022

## Essentials Addons "According to me"

```bash
sudo pacman -S plocate noto-fonts-cjk evince flameshot wget lxappearance mpd peek mpv neovim yarn xclip feh python-pip github-cli nomacs deno polybar alacritty telegram-desktop noto-fonts-emoji libreoffice-fresh nodejs-lts-hydrogen linux-lts discord inxi xfce4-notifyd gnome-user-share rofi htop wine gnome-disk-utility gyp xf86-video-nouveau lib32-mesa mesa obsidian opera opera-ffmpeg-codecs gnome-terminal neovide lazygit
```

```bash
# install node version manager
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

```bash
yay -S mmv appimagelauncher microsoft-edge-stable-bin vundle stacer-bin sublime-text-4 lite-xl pnpm-bin vscodium-bin google-chrome android-sdk easyeda-bin  easyeda-pro-bin balena-etcher-electron-bin
```

## zsh package and it's plugins

```bash
sudo pacman -S zsh zsh-autosuggestions zsh-completions zsh-syntax-highlighting zsh-theme-powerlevel10k
```

```bash
sudo git clone https://github.com/popstas/zsh-command-time.git /usr/share/zsh/plugins/zsh-command-time
```

## bluetooth support

```bash
# install required packages
sudo pacman -S blueberry blueman

# start bluetooth
sudo systemctl start bluetooth
```

## steganography

```bash
sudo pacman -S hexedit foremost binwalk
```

```bash
yay -S steghide
```

## Colloid-gtk-theme requirements

```bash
sudo pacman -S gtk-engine-murrine
```

## Bug bounty hunting

**Note :** Blackarch repository should be added

```bash
sudo pacman -S nmap android-apktool hashcat sqlmap john cuda freerdp httpie maven tcpdump masscan minder composer php-gd docker docker-compose python-netifaces evil-winrm mariadb postgresql openvpn php redis gunicorn metasploit tree man-db man-pages bind ack fzf postgresql
```

burpsuite can be intalled manually using sudo

```bash
yay -S rockyou naabu mkpasswd xampp klogg-bin
```

## Hugo

```bash
sudo pacman -S hugo dart-sass sassc npm
```

## Qt

```bash
sudo pacman -S qt5-imageformats qt5-multimedia qt5-speech qt5-svg qt5-tools qt5-wayland qt5-x11extras
```

## Design

penpot(Manual(Docker))
https://help.penpot.app/technical-guide/getting-started/

## Tools i had to use while studying in university

### octave

```bash
sudo pacman -S octave
```

```bash
# addons
yay -S octave-control octave-statistics
```

### Kicad

```bash
sudo pacman -S kicad kicad-library kicad-library-3d
```

## Printer Hp

```bash
sudo pacman -S hplip simple-scan libhandy usbutils xsane python-pillow cups python-pyqt5
sudo pip install pyqt5
sudo systemctl enable --now cups
sudo systemctl start --now cups
sudo hp-setup
```

## fyne

A Cross platform GUI toolkit in Go inspired by Material Design

```bash
sudo pacman -S go xorg-server-devel libxcursor libxrandr libxinerama libxi
```

## flutter

```bash
# install dependencies
sudo pacman -S cmake clang llvm-libs pkg-config ninja gradle

sudo pacman -S jre11-openjdk
```

```bash
# install android studio and it's dependicies
yay -S  android-studio
yay -S android-sdk android-sdk-platform-tools android-sdk-build-tools android-sdk-cmdline-tools-latest
yay -S android-platform

# install flutter
yay -S flutter
```

## web3

```bash
sudo pacman -S solidity solana
```

## run windows software

```bash
sudo pacman -S wine
yay -S playonlinux
```

## pic programming

```bash
sudo pacman -S sdcc
```

## mongodb

```bash
# mongodb version 4
yay -S mongodb44-bin mongosh-bin mongodb-tools-bin
```

## arduino using yay

```bash
# i had to install all of these to make it work
yay -S arduino-ide-bin
sudo pacman -S arduino arduino-avr-core arduino-builder arduino-cli arduino-ctags arduino-docs

sudo chmod a+rw /dev/ttyUSB0
# or ttyUSB1 it depends on the usb port you are using
```

## nvchad

```bash
yay -S nerd-fonts-inter repgrep nvim-packer-git
git clone https://github.com/NvChad/NvChad ~/.config/nvim --depth 1 && nvim
```

## fritzing (tinkercad is better)

```bash
yay -S fritzing
```

## Install WoeUSB on Linux

```bash
sudo pacman -S p7zip python-pip python-wxpython
git clone https://github.com/WoeUSB/WoeUSB-ng
cd WoeUSB-ng
sudo pip3 install .
sudo woeusbgui &
```
