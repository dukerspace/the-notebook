---
id: ubuntu
title: Ubuntu
type: docs
path: the-notebook/ubuntu
---

## Ubuntu

- uptime : check time use on computer

#### remove app

- sudo apt-get purge <name>
- sudo apt autoremove

#### switch to gui mode

- Ctrl + Alt + F7

#### check port used

```
sudo lsof -t -i:80
```

#### stop process by port

```
sudo kill `sudo lsof -t -i:80`
```

#### check disk free

```
df -h
```

#### add user

- adduser <username>

```
adduser dukerspace
```

#### add root privileges

- visudo

```
user ALL=(ALL:ALL)ALL
```

#### remove user

- userdel <username>

```
userdel dukerspace
```

#### set timezone

```
sudo timedatectl set-timezone Asia/Bangkok
```

#### check timezone

```
timedatectl
timedatectl status | grep "Time zone"
```

---

#### Password using SSH

- Find path

```
/etc/ssh/sshd_config
```

- Look for the line which reads:

```
PasswordAuthentication no
```

and change it to

```
PasswordAuthentication yes
```

Save the file.

```
sudo passwd $USER
```

#### tree

tree <folder>

```
tree media
```

### app

- tmux
- htop

### login as root

```
sudo -i
```

### change user

sudo -u <user> -s

```
sudo -u ubuntu -s
```

### find file

```

https://www.plesk.com/blog/various/find-files-in-linux-via-command-line/

```

### find large file

```
sudo du -a / 2>/dev/root | sort -n -r | head -n 20
```
### harddisk used
```
df -h
```

### ram used
```
free -h
```
