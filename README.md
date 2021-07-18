# BackupFriend-docker

This docker container used as a server-side to sync backups to [backupfriend-client](https://github.com/guysoft/backupfriend-client)

It is also the base or the RaspsberryPi dedicated distro 

## RaspberryPi

    cd src
    docker-compose build
    docker-compose up -d

## Cloud server

    mkdir backupfriend-server
    cd backupfriend-server
    wget https://raw.githubusercontent.com/guysoft/BackupFriend-docker/master/src/docker-compose.yml
    wget https://raw.githubusercontent.com/guysoft/BackupFriend-docker/master/src/env_server
    wget https://raw.githubusercontent.com/guysoft/BackupFriend-docker/master/src/rdw.conf
    mv env_server .env
    touch rdw.db
    sudo docker network create nginx-proxy
    sudo docker-compose up -d
    
    

## Build and run

    cd src
    docker-compose build
    docker-compose up -d

# Containers on docker hub:
* [ssh container on Docker Hub](https://hub.docker.com/repository/docker/guysoft/backupfriend-ssh)
* [webserver container on Docker Hub](https://hub.docker.com/repository/docker/guysoft/backupfriend)
* Web server uses [rdiffweb](https://gitlab.com/ikus-soft/rdiffweb/)
  * Default user and password is user: ``admin`` , password: ``admin123`` like in the demo of rdiffweb


* rdiffweb instance is at port 8082 eg: http://backupfriend.local:8082
* ssh to sync rdiff-backup is at port at 8022 eg: http://backupfriend.local:8022
