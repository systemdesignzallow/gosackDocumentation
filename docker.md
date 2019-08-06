# Docker

## References

https://phoenix-sei.slack.com/archives/DKJ4FGF62/p1564711822000400

## Shell Script

```sh
#!/bin/bash
git clone https://github.com/systemdesignzallow/gosackService
cd gosackService
git checkout docker

echo 'LOCAL_SERVICE_SERVER_PORT=6001' >> .env
echo 'NODE_ENV="docker"' >> .env
echo 'NEW_RELIC="ab77636d6d1a81e91b0b1326702da84ae52124a9"' >> .env
echo 'DOCKER_DB_HOST="54.190.198.143"' >> .env
echo 'DOCKER_DB_PORT=3306' >> .env
echo 'DOCKER_DB_USER="root"' >> .env
echo 'DOCKER_DB_PW="mypassword"' >> .env
echo 'DOCKER_DB="gosackDB"' >> .env

sudo docker pull node:11.15.0
sudo docker build -t gosackservice .
# HOLY CRAP THAT PORT STUFF IS IMPORTANT!
sudo docker run -itd -p 80:6001 --name newservice gosackservice
```

## Docker images

[Good Resource for Docker Commit](https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html)

## Helpful Commands

`docker logs $container_id`
see logs of docker instance

`docker ps -a`
see all containers

`docker rm [name]`
remove container

`docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name_or_id`

get ip for docker container

## Commands for gosackService container

`docker pull node:11.15.0`
`docker build -t gosackservice .`
`sudo docker run -itd -p 6001:6001 --name newservice gosackservice`
No interactive shell
`sudo docker run -it -p 6001:6001 --name newservice gosackservice /bin/bash`
with shell
ekauqquake69

sudo docker pull pgosack/gosackservice

## Commands for gosackDB container

`docker pull mariadb/server:10.3`
`docker build --build-arg MARIADB_ROOT_PASSWORD=mypassword -t gosackdb .`
`sudo docker run -d --name newdb -eMARIADB_ROOT_PASSWORD=mypassword gosackdb`
`sudo docker exec -it newdb curl https://gosackdata.s3-us-west-1.amazonaws.com/small.csv -o /var/lib/mysql/data.csv`
`sudo docker exec -it newdb mysql -u root -p$MARIADB_ROOT_PASSWORD < bootstrap.sql`
`sudo docker exec -it newdb /bin/bash`

`sudo docker run -eMARIADB_ROOT_PASSWORD=mypassword -d -p 3306:3306 mysql:5.7.13`
`mysql -hlocalhost --protocol=TCP -uroot -p1234`
`sudo docker run -d --name newdb -p 3306:3306 -e MARIADB_ROOT_PASSWORD=mypassword gosackdb`
`sudo docker exec -it newdb mysql -hlocalhost --protocol=TCP -u root -p\$MARIADB_ROOT_PASSWORD`
`sudo docker exec -it newdb curl https://gosackdata.s3-us-west-1.amazonaws.com/bootstrap.sql -o bootstrap.sql`
`https://gosackdata.s3-us-west-1.amazonaws.com/bootstrap.sql`
`docker run -d -p 12345:3306 my-image`

`mysql --protocol=TCP -h 54.190.198.143 -u root -pmypassword`

## Dockerfile

- Dockerfile
- pull mariadb image

* transfer all files to setup db
* expose 3306
* execute

## bootstrap

- bootstrap script
- install docker on ec2
- docker pull mariadb
- execute docker stuff

## infrastructure

- typescript
- cdk
