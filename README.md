# My SAP CA2 Main
# SAPCA2

# Setting up a MySQL and phpMyAdmin environment with Docker

## Creating a Docker network

To create a Docker network use the following command:

```
docker network create my-network
```

This command creates a new Docker network with the name 'my-network'.

## Running a MySQL Docker container

To run a MySQL Docker container with the name of db and a root password of my-secret-password, use the following command:

```
docker run --name db -e MYSQL_ROOT_PASSWORD=my-secret-password --network my-network -d mysql:latest
```
This command runs a new Docker container based on the latest version of the MySQL Docker image, with the name 'db' and a root password of 'my-secret-password'. The container is connected to the 'my-network' Docker network. mysql:latest is specifying the MySQL version you want which in this case is the latest. 

## Running phpMyAdmin on the Docker network

To run phpMyAdmin on the Docker network, use the following command:

```
docker run --name phpmyadmin -d --network my-network -p [your port]:80 phpmyadmin/phpmyadmin
```

This command runs a new Docker container based on the phpMyAdmin Docker image, with the name 'phpmyadmin'. The container is connected to the 'my-network' Docker network and maps a port of your choice to port 80 of the container. Replace [your port] with the port you want to use to access phpMyAdmin in your browser.

command references where taken for the docker official documentation where the code was tweaked a little to the question given on the CA  

##Documentation
For more information on the mysql and phpmyadmin Docker images and their available option at the official documentation:

- Docker network create: https://docs.docker.com/engine/reference/commandline/network_create/
- MySQL: https://hub.docker.com/_/mysql
- phpMyAdmin: https://hub.docker.com/_/phpmyadmin" > README.md
