To create a docker network on a specific subnet, run:
```
docker network create --subnet=172.19.0.0/16 ansible_test_network

```

Then, add two containers to the network:
```
docker run -d --network ansible_test_network --ip 172.19.0.2 --name ansible1 ssh_docker_test
docker run -d --network ansible_test_network --ip 172.19.0.3 --name ansible2 ssh_docker_test
```
