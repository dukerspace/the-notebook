- https://certbot.eff.org/lets-encrypt/ubuntubionic-nginx

```
version: '3.3'
services:
  reverse-proxy:
    build: .
    # image: artisandigitalasia/revers-proxy
    ports:
      - 80:80
      - 443:443
    volumes:
       - ./letsencrypt:/var/www/letsencrypt
  portainer:
    image: portainer/portainer:latest
    command: -H unix:///var/run/docker.sock
    restart: always
    ports:
       - 12144:9000
       - 12145:8000
    volumes:
       - /var/run/docker.sock:/var/run/docker.sock
       - ./portainer_data:/data
```

```
   # for re-new
   # location ^~ /.well-known {
   #   allow all;
   #   alias /var/www/letsencrypt/.well-known/;
   #   default_type "text/plain";
   #   try_files $uri =404;
   #}
   #location ^~ /.well-known/acme-challenge/ {
   #   allow all;
   #   alias /var/www/letsencrypt/.well-known/acme-challenge/;
   #}

```
