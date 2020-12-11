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

docker-compose_postgres.yml
----------------------------

This will create postgres container as per the database.env file configured in the main folder

docker-compose_jenkins.yml
---------------------------
This will create jenkins container as per the image name given in compose file.You may need to change image,ports,volume etc


docker-compose_postgres2.yml
-----------------------------
It will create postgres latest  container with the db user:postgres & passwd :postgres

login into postgres docker continer
-----------------------------------

docker exec -it <containername/containerid> bash

root@e7f5f96b140a:/# su postgres
postgres@e7f5f96b140a:/$ psql
psql (13.1 (Debian 13.1-1.pgdg100+1))
Type "help" for help.

postgres=# exit


