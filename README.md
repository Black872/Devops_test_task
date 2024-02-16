# Devops_test_task
Test tasks with Docker/docker-compose, ansible, terraform

1.
Command to run ansible container
docker build -t ansible:v1 --build-arg ssh_prv_key="$(cat ~/.ssh/id_rsa)" --build-arg ssh_pub_key="$(cat ~/.ssh/id_rsa.pub)" --squash .

docker run --rm -it --network host --name ansible_cont ansible:v1 

