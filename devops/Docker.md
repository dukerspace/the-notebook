
### Docker

#### use command
docker exec -it <container_name> <command>
- ex: docker exec -it docker_test bash

#### copy
docker cp <file> <container_name>:/<path>
- ex host to container: docker cp rabbitmqadmin docker_rabbitmq_1:/usr/local/bin
- ex container to host: docker cp jenkins:/var/jenkins_home/secrets/initialAdminPassword C:/Users/tdcm025

#### remove file
docker exec <container_name> rm -rf <file>
- ex: docker exec docker_rabbitmq_1 rm -rf rmq-setup.sh

#### remove volume data
docker volume ls
docker volume rm <name>
- ex: docker volume rm docker_rabbitmq-data
- ex remove all volume: docker volume rm `docker volume ls -q -f dangling=true`

removing only unused volumes:
- docker volume prune

#### image
- docker image prune : remove none used


### Docker Compose

#### run
- docker-compose run -d --build

#### build
- docker-compose build