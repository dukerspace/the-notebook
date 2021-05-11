---
id: pi
title: pi
type: docs
path: the-notebook/pi
---

## connect wifi

- wpa_supplicant.conf

```
country=TH
update_config=1
ctrl_interface=/var/run/wpa_supplicant
network={
 ssid="Artisan HQ"
 psk="Artisan"
}
```

## hostname

sudo nano /etc/hosts

```
127.0.0.1 eastbar
```

## set on boot

- rc.local

```

```

```

package main

import (
    "bytes"
    "log"
    "os/exec"
)

func main() {
    cmd := exec.Command("omxplayer", "-o",  "hdmi", "test.mp4" )
    var out bytes.Buffer
    cmd.Stdout = &out
    err := cmd.Run()
    if err != nil {
        log.Fatal(err)
    }
}

```
