# Docker

## References

https://phoenix-sei.slack.com/archives/DKJ4FGF62/p1564711822000400

## Helpful Commands

`docker logs $container_id`
see logs of docker instance

`docker ps -a`
see all containers

`docker rm [name]`
remove container

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
