# docker-compose-mysql

This repo contains customise docker-compose for mysql.
You can edit image,container_name,ports,environment,volume directory
run dockercompose from a custom directoy: docker-compose up

to run in backgroud : docker-compose up -d

login into mysql container:
docker exec -it containername/containerid bash
docker exec -it containername/containerid /bin/bash

login mysql from container:
1.mysql -uroot -p
enter root password
2.mysql -u root -p
enter root password

docker-compose.ymlwithsqlscripts
--------------------------------
This docker compose will create mysql container with sql scripts given in sql-scripts folder .This must be in the root folder for docker-compose
sometimes you need to down docker compose by:docker-compose down before up.

docker-compose.ymlwithmysql+apache
-----------------------------------
First need to have a Dockerfile & index.html with below contents in project folder 

FROM ubuntu:16.04

RUN apt-get update \
   && apt-get install -y apache2

COPY index.html /var/www/html/
WORKDIR /var/www/html
CMD ["apachectl", "-D", "FOREGROUND"]
EXPOSE 80

index.html: 
<h2>It Works</h2>
Welcome to Docker Compose Tutorial

then run commands :

To build docker image as per the Docker file -docker-compose build
To run docker containers -docker-compose up
docker-compose up -d 

