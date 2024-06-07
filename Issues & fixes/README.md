# Issues & Fixes

## CloudflareWARP daemon

**Issue** 🛑

Unable to connect to CloudflareWARP daemon. Maybe the daemon is not running?

**Fix** ✅

```bash
sudo systemctl enable --now warp-svc.service
```

## running vnstat

**Issue** 🛑

Error: Unable to open database directory "/var/lib/vnstat": No such file or directory The vnStat daemon should have created this directory when started. Check that it is configured and running. See also "man vnstatd".

**Fix** ✅

```bash
sudo systemctl start vnstat
```

## Terminal Emulator

**Issue** 🛑

Failed to launch preferred application for category “TerminalEmulator”

**Fix** ✅

```bash
# open config file
gedit ~/.config/xfce4/helpers.rc

# add your prefered terminal emulator
TerminalEmulator=kitty
```

## setup Time

**Issue** 🛑

time not set properly

**Fix** ✅

```bash
timedatectl set-timezone Africa/Algiers
timedatectl set-ntp true
```

## Docker Starting Problem

**Issue** 🛑

Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?

**Fix** ✅

```bash
sudo systemctl start docker
```

## mysql won't start

**Issue** 🛑

ERROR 2002 (HY000): Can't connect to local server through socket '/run/mysqld/mysqld.sock'

**Fix** ✅

```bash
sudo -s
cd /var/lib/mysql
ls
rm -r \*
mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
systemctl start mysqld
systemctl start mysql.service
systemctl start mariadb
mysql
```

## Missing go.sum entry for module ....

**Issue** 🛑

missing go.sum entry for module providing package

**Fix** ✅

```bash
go mod tidy
```

## flutter running as sudo

**Issue** 🛑

flutter permission

**Fix** ✅

```bash
sudo chown -R $USER /opt/flutter
```

## change node version

**Issue** 🛑

node compatibility issues

**Fix** ✅

```bash
nvm install 16
nvm alias default v16.17.0
nvm use 16.17.0
node -v
```

## dart library

**Issue** 🛑

The library "....." is legacy, and should not be imported into a null safe library in dart

**Fix** ✅

```bash
dart pub outdated --mode=null-safety
# and then upgrade all your dependencies to null-safety
dart pub upgrade --null-safety
```

## java version

### check java version installed on arch linux

```bash
java -version
```

### list all installed versions

```bash
archlinux-java status
```

### to switch to a different java version

```bash
sudo archlinux-java set <java_version>
# list again
archlinux-java status
```
