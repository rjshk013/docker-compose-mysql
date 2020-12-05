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
