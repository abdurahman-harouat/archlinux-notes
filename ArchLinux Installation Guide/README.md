# Archlinux installation guide

**Note:** this is for non non-UEFI system, for more details you can visit [It's foss website](https://itsfoss.com/install-arch-linux/)

## list available disks

```bash
fdisk -l
```

## select the disk you are going to format

```bash
fdisk /dev/sda1

# i usually delete any existing partitions on the disk using command d

# Once you have the entire disk space free, you can create a new partition using command n
```

## create a file system

```bash
mkfs.ext4 /dev/sda1
```

## refresh mirrorlists

```bash
pacman -Syy
pacman -S reflector
cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.bak

# i'm using korean server for speed
reflector -c "KR" -f 12 -l 10 -n 12 --save /etc/pacman.d/mirrorlist
```

## mounting

```bash
mount /dev/sda1 /mnt
```

## installing essential software "according to me"

**Note:** i'm using i3 window manager

```bash
pacstrap /mnt base linux linux-firmware vim nano sudo networkmanager gedit i3-gaps sddm thunar thunar-archive-plugin kitty gvfs-mtp file-roller chromium git base-devel go reflector
```

## Generate a fstab

```bash
# Generate a fstab file to define how disk partitions, block devices, or remote file systems are mounted into the filesystem.

genfstab -U /mnt >> /mnt/etc/fstab
```

## Enter the mounted disk as root

```bash
arch-chroot /mnt
```

## Setting Time (sometimes it does not work)

```bash
timedatectl set-timezone Africa/Algiers
```

## Setting system language

Set up locale, for me uncomment ar_DZ UTF-8 in locale.gen:

```bash
nano /etc/locale.gen
locale-gen
echo LANG=ar_DZ.UTF-8 > /etc/locale.conf
export LANG=ar_DZ.UTF-8
```

## Setting a hostname

```bash
echo ghazi > /etc/hostname
```

## Create hosts file

```bash
# create file
touch /etc/hosts

# open file in nano editor
nano /etc/hosts

# add this to the file
127.0.0.1 localhost
::1 localhost
127.0.1.1 ghazi
```

## Setting password for root user

```bash
passwd

# then set a new password
```

## installing grub

```bash
pacman -S grub

grub-install /dev/sda

grub-mkconfig -o /boot/grub/grub.cfg
```

## enabling services

```bash
# enable login manager and network manager
systemctl enable sddm
systemctl enable NetworkManager
```

## add user

```bash
useradd -m ghazi

# set a password for the user to be able to login
passwd ghazi
```

## add user to sudoers

```bash
# add user to a group of users that grants specific permissions.
usermod -aG wheel,audio,video,storage ghazi
```

```bash
# It opens in VI editor by default. So we need to force it use nano
EDITOR=nano visudo
```

uncomment this by removing hashtag

```bash
# %wheel ALL=(ALL:ALL) ALL
%wheel ALL=(ALL:ALL) ALL
```

Add this

```bash
root ALL=(ALL:ALL) ALL
ghazi ALL=(ALL:ALL) ALL
```

## umount

```bash
exit
umount /mnt
```

## final step

```bash
reboot #or shutdown now
```
