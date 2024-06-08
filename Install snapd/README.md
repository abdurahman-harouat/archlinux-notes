## install snapd

```bash
git clone https://aur.archlinux.org/snapd.git
cd snapd
makepkg -si

# enable snapd
sudo systemctl enable --now snapd.socket

# create a symlink
sudo ln -s /var/lib/snapd/snap /snap
```
