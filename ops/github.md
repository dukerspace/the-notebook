---
id: github
title: Git Hub
type: docs
path: the-notebook/ops/github
---

## Github Runner

- สร้าง account กลาง (github)
- ให้ access iam gcp

## check disk in runner

- remove old project

```
/actions-runner/_work
```

If you want the runner to start automatically when the server boots, use the built-in service script:
```
sudo adduser github-runner
sudo usermod -aG docker github-runner  # if you want Docker builds
su - github-runner

sudo ./svc.sh install
sudo ./svc.sh start
```

Check status:
```
sudo ./svc.sh status
```

Stop the service:
```
sudo ./svc.sh stop
```

✅ This is the only place where sudo is allowed — because you’re installing a system service.

🧹 Option 3: Uninstall or Reconfigure

To remove the service:
```
sudo ./svc.sh stop
sudo ./svc.sh uninstall
```

To reconfigure the runner:
```
./config.sh remove
```

Fix (recommended): Add github-runner to the docker group
```
sudo groupadd docker 2>/dev/null || true
sudo usermod -aG docker github-runner
sudo su - github-runner
```