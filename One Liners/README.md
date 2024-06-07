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
