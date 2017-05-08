
command
docker exec -it <container_name> <command>
ex: docker exec -it docker_test bash

copy
docker cp <file> <container_name>:/<path>
ex: docker cp rabbitmqadmin dockertradition_rabbitmq_q:/usr/local/bin
