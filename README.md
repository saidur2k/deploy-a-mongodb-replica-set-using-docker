# deploy-a-mongodb-replica-set-using-docker

3 docker containers.
- 1x manager -> Manager 1
- 2x secondary for replication -> Worker 1 and Worker 2

## Manager 1
- Docker Container name: mongoNode1
- Docker volume
- IP: 192.168.99.100

## Worker 1
- Docker Container name: mongoNode2
- Docker volume
- IP: 192.168.99.101

## Worker 2
- Docker Container name: mongoNode3
- Docker volume
- IP: 192.168.99.102

# Requirements

- docker and docker-machine installed
- VirtualBox on MacOS Sierra to run our mongoDB instances

# Step 1 — Create our 3 docker-machines

To create a docker machine we need to issue the next command in a terminal:

`$ docker-machine create -d virtualbox manager1`

This command will create a machine called manager1 using virtualbox as our virtualization provider.

Now let’s create the two secondary docker-machines


# Helpful commands

## docker-machine ls
Shows a list of docker-machines

`$ docker-machine ls`
|NAME   |ACTIVE   |URL          |STATE     |URL                         |SWARM   |DOCKER   |ERRORS|
|-------|:-------:|:------------|:---------|:---------------------------|:------:|:-------:|------|
|bar    |-        |virtualbox   |Running   |tcp://192.168.99.101:2376   |        |v1.9.1   |      |
|baz    |-        |virtualbox   |Running   |tcp://192.168.99.103:2376   |        |v1.9.1   |      |
|foo    |-        |virtualbox   |Running   |tcp://192.168.99.100:2376   |        |v1.9.1   |      |
|qix    |-        |virtualbox   |Running   |tcp://192.168.99.102:2376   |        |v1.9.1   |      |

## docker-machine rm
Remote a docker machine



`$ docker-machine rm baz`
About to remove baz
Are you sure? (y/n): y
Successfully removed baz

## docker-machine remove all
`$ docker-machine rm -y $(docker-machine ls -q)`
