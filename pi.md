# pi

## connect wifi

- wpa_supplicant.conf

```
country=TH
update_config=1
ctrl_interface=/var/run/wpa_supplicant
network={
 ssid="Artisan HQ"
 psk="SenseOfOwnership"
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
