# Helpful one liners

**removing hashtag comments**

```bash
sudo sed -i 's/^\#.\*$//g' file.txt
```

**Adding a host to /etc/hosts "related to hackthebox"**

```bash
sudo sh -c 'echo "10.129.178.255 unika.htb" >> /etc/hosts'
```

**delete last line**

```bash
sudo sed -i '$ d' /etc/hosts
```

**install bunjs**

```bash
curl https://bun.sh/install | bash
```

**install pnpm**

```bash
curl -fsSL https://get.pnpm.io/install.sh | sh -
```

**install vim-plug**

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
