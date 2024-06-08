# Switch from i3 to bspwm

## Install bspwm and its dependencies:

Open a terminal and run the following command to install bspwm and its required packages:

```bash
sudo pacman -S bspwm sxhkd
```

## Create the necessary configuration files:

By default, bspwm looks for its configuration files in the ~/.config/bspwm/ directory. Create this directory if it doesn't exist:

```bash
mkdir -p ~/.config/bspwm/
```

Next, create the bspwmrc file, which is the main configuration file for bspwm:

```bash
touch ~/.config/bspwm/bspwmrc
```

Similarly, create the sxhkdrc file, which is used for configuring keybindings for bspwm:

```bash
touch ~/.config/sxhkd/sxhkdrc
```

## Configure bspwm:

Open the bspwmrc file in a text editor and add the desired configuration options. Here's a basic example to get you started:

```bash
#!/bin/bash
...

# Set the wallpaper
feh --bg-fill /home/ghazi/Pictures/eid2020.jpg &

# Launch the status bar (e.g., polybar)
polybar --config=/home/ghazi/.config/polybar/config.ini &
```

## Initialize bspwm

```bash
bspwm
```

## make it executable:

```bash
chmod +x ~/.config/bspwm/bspwmrc
```

## Configure sxhkd:

Open the sxhkdrc file in a text editor and set up your keybindings. Here's an example of some common keybindings:

```bash
# terminal (alacritty)
super + Return
    alacritty

# Close focused window
super + q
    bspc node -c

# Switch focus between windows
super + {h,j,k,l}
    bspc node -f {west,south,north,east}

# Restart bspwm
super + Shift + r
    bspc wm -r
```

Save the file.

## Set up xinitrc:

### Step 1: Edit ~/.xinitrc

Open your ~/.xinitrc file in a text editor and modify it to launch bspwm:

```bash
#!/bin/bash

# ~/.xinitrc

# Executed by startx (run your window manager from here)

# Set the default cursor theme
xsetroot -cursor_name left_ptr

# Launch bspwm
exec bspwm
```

### Step 2: Remap Modifier Keys Using xmodmap

To use the Alt key as the Super key in bspwm, you'll need to remap the modifier keys using xmodmap. Follow these steps:

1. Install xorg-xmodmap

If you don't already have it installed, run the following command to install xorg-xmodmap:

```bash
sudo pacman -S xorg-xmodmap
```

2. Create a New xmodmap File

Create a new file named .xmodmaprc (or any name you prefer) in your home directory:

```bash
touch ~/.xmodmaprc
```

3. Edit the xmodmap File

Open the ~/.xmodmaprc file in a text editor and add the following lines:

```bash
clear Mod1
add Mod4 = Alt_L
```

These lines clear the original Alt modifier (Mod1) and assign the Super modifier (Mod4) to the left Alt key (Alt_L).

4. Load the xmodmap Configuration

To load the xmodmap configuration on startup, open your ~/.xinitrc file in a text editor and add the following line before launching bspwm:

```bash
xmodmap ~/.xmodmaprc &
```

Save the file.

5. Restart bspwm

Restart bspwm for the changes to take effect. You can either log out and log back in or restart Xorg.

**Now, the Alt key should function as the Super key in bspwm. You can use it for keybindings and commands that are typically triggered by the Super key.**
