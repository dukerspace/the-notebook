---
id: docker
title: Docker
type: docs
path: the-notebook/ops/docker
---

### Docker

#### Build image

docker build -t ${IMAGE}:${VERSION} \${LOCATION}

```
docker build -t hub.dezenter.org/dezenter/web:0.1.0 .
```

#### tag image to private registry

- docker image tag <local_image:tag> <host>/<host_image:tag>

```
docker image tag dezenter/air:0.1.0 hub.dezenter.org/dezenter/air:0.1.0
```

####

- docker (hub) image push <username>/<project_name>:<tag_version>
- docker (private) image push <url>/<namespace>/<project_name>:<tag_version>

```
docker image push hub.dezenter.org/dezenter/air:0.1.0
```

#### run image

```
docker run --publish 8080:8080 --detach --name bb -t bulletinboard:1.0
```

#### use command

- docker exec -it <container_name> <command>

```
docker exec -it docker_test bash
```

#### copy

docker cp

- host to container <file> <container_name>:/<to_path>

```
docker cp rabbitmqadmin docker_rabbitmq_1:/usr/local/bin
```

- container to host <container_name>:/<path>/<file> <to_path>

```
docker cp jenkins:/var/jenkins_home/secrets/initialAdminPassword C:/Users/tdcm025
```

#### remove file

- docker exec <container-name> rm -rf <file>

```
docker exec docker_rabbitmq_1 rm -rf rmq-setup.sh
```

#### remove volume data

- docker volume ls
- docker volume rm <name>

```
docker volume rm docker_rabbitmq-data
```

- ex remove all volume

```
docker volume rm `docker volume ls -q -f dangling=true`
```

- removing only unused volumes:

```
docker volume prune
```

#### image prune

-remove none used

```
docker image prune
```

#### remove all images

```
docker images -q | xargs docker rmi -f

docker image ls -q | xargs -I {} docker image rm -f {}
```

#### container

```
docker container prune => remove none used container
```

#### check disk

```
docker system df
```

### Docker Compose

- This removes all the containers

```
docker-compose down -v --rmi all
```

#### Build image

##### version 3

- links: ผูก service เข้าด้วยกัน รูปแบบ Sevice name:Alias name
- depens_on: start service หลังจาก service ที่อยู่ depend on เริ่มต้นการทำงานเสร็จแล้ว

#### run

- docker-compose run -d --build

```
docker-compose -f docker-compose-production.yml up -d
```

#### build

- docker-compose build

#### exec

- docker-compose exec -it <name> bash

#### .env

- ใน environment ใช้ $$ => ex: VAR=$${VARS}

#### link

- [training](https://training.play-with-docker.com)

--remove-orphans

### permission docker

```
sudo chmod 666 /var/run/docker.sock
```
