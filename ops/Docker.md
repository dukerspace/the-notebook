
### Docker

#### use command
docker exec -it <container_name> <command>
- ex: docker exec -it docker_test bash

#### copy
docker cp 
##### ex host to container <file> <container_name>:/<to_path>
- docker cp rabbitmqadmin docker_rabbitmq_1:/usr/local/bin
##### ex container to host <container_name>:/<path>/<file> <to_path>
- docker cp jenkins:/var/jenkins_home/secrets/initialAdminPassword C:/Users/tdcm025

#### remove file
docker exec <container-name> rm -rf <file>
- ex: docker exec docker_rabbitmq_1 rm -rf rmq-setup.sh

#### remove volume data
docker volume ls
docker volume rm <name>
- ex: docker volume rm docker_rabbitmq-data
- ex remove all volume: docker volume rm `docker volume ls -q -f dangling=true`

removing only unused volumes:
- docker volume prune

#### image
- docker image prune => remove none used

#### container
- docker container prune => remove none used container

### Docker Compose

#### docker-compose.yml
##### version 3
- links:  ผูก service เข้าด้วยกัน รูปแบบ Sevice name:Alias name
- depens_on: start service หลังจาก service ที่อยู่ depend on เริ่มต้นการทำงานเสร็จแล้ว

#### run
- docker-compose run -d --build

#### build
- docker-compose build

#### exec
- docker-compose exec <name> bash

#### .env
- ใน environment ใช้ $$ => ex: VAR=$${VARS}

#### link
- [training](https://training.play-with-docker.com)