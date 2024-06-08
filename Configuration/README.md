# Some configurations

## Make Z shell as the default shell

```bash
# print current shell
echo $SHELL
# make Z shell the default one
chsh -s /usr/bin/zsh
```

## Enable the multilib repository in the pacman.conf file

```bash
# open file on gedit editor
sudo gedit /etc/pacman.conf
```

uncomment `[multilibe]` and include

```bash
[multilib]
Include = /etc/pacman.d/mirrorlist
```

Finally run

```bash
sudo pacman -Syy
```

## Adding Fonts

Download font from google for example

Copy font in ~/.local/share/fonts

## Change icons

you can use lxappearance to change icons

## i3 config

```bash
# Font for window titles.
font pango: Tajawal 10
```

## Adding rofi themes

Copy themes in ~/.local/share/rofi/themes

## Enable & start bluetooth service

```bash
sudo systemctl enable bluetooth.service
sudo systemctl start bluetooth.service
```

## Adding go variable envirement

copy this in .zshrc

```bash
export GOROOT=/usr/lib/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
```

then run

```bash
source ~/.zshrc
```

then logout and login

## adding polybar

go to `~/.config/polybar/` and run the following

```bash
cd ~/.config/polybar/
./launch.sh --forest
```

## xfce4 notifyd configuration

```bash
xfce4-notifyd-config
```

## running excalidraw

```bash
sudo systemctl start docker
sudo docker pull excalidraw/excalidraw:latest
sudo docker run --rm -dit --name excalidraw -p 5000:80 excalidraw/excalidraw:latest
```

then go to localhost:5000
