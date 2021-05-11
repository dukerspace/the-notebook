ssh -i ~/.ssh/gcp_montol montol@35.247.141.14

autossh -M 10001 -N -R 10000:localhost:22 tunnel

autossh -M 10004 -N -R 10003:localhost:22 tunnel

ssh -N -R 10003:localhost:22 tunnel

ssh -N -L 9090:localhost:10000 montol@tunnel

ssh montol@tunnel -p 9090

---

## Config

- gen rsa

```
ssh-keygen -t rsa
```

- copy public key to gpc vm -> Metadata -> ssh keys

```
cat ./.ssh/id_rsa.pub
```

- config ssh
  nano ./.ssh/config

```
Host tunnel
  HostName 35.247.141.14
  User pi
  IdentityFile ~/.ssh/id_rsa
  IdentitiesOnly yes
``
- install autossh
```

sudo apt install autossh -y

```

- set pi
- pi 1
```

autossh -M 10001 -N -R 10000:localhost:22 tunnel

```

- pi 2
```

autossh -M 10003 -N -R 10002:localhost:22 tunnel

```
[program:ssh-forward]
process_name=%(program_name)s_%(process_num)02d
command=/usr/bin/autossh -M 10001 -N -R 10000:localhost:22 tunnel
autostart=true
autorestart=true
user=root
numprocs=1
redirect_stderr=true
stdout_logfile=/var/log/ssh-forward.log
```

## login by my computer

```
ssh -N -L 9090:localhost:10000 montol@tunnel

```

```
ssh pi@localhost -p 9090
```

---

## check port

```

netstat -tulpn | grep 10000
netstat -tulpn | grep 10001

```
