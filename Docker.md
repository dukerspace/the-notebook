
command
docker exec -it <container_name> <command>
ex: docker exec -it docker_test bash

copy
docker cp <file> <container_name>:/<path>
ex: docker cp rabbitmqadmin dockertradition_rabbitmq_1:/usr/local/bin

remove file
docker exec <container_name> rm -rf <file>
ex: docker exec dockertradition_rabbitmq_1 rm -rf rmq-setup.sh
