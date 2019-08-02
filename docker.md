# Docker

## References

https://phoenix-sei.slack.com/archives/DKJ4FGF62/p1564711822000400

## Dockerfile

- Dockerfile
- pull mariadb image
  `docker pull mariadb/server:10.3`
  `sudo docker run -d --name maria -eMARIADB_ROOT_PASSWORD=mypassword mariadb/server:10.3`
  `sudo docker exec -it maria /bin/bash`

- transfer all files to setup db
- expose 3306
- execute

## bootstrap

- bootstrap script
- install docker on ec2
- docker pull mariadb
- execute docker stuff

## infrastructure

- typescript
- cdk
