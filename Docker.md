
command
docker exec -it <container_name> <command>
ex: docker exec -it docker_test bash

copy
docker cp <file> <container_name>:/<path>
ex host to container: docker cp rabbitmqadmin dockertradition_rabbitmq_1:/usr/local/bin
ex container to host: docker cp jenkins:/var/jenkins_home/secrets/initialAdminPassword C:/Users/tdcm025

remove file
docker exec <container_name> rm -rf <file>
ex: docker exec dockertradition_rabbitmq_1 rm -rf rmq-setup.sh
