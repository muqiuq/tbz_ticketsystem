# tbz_ticketsystem

Disclaimer: Do not use these docker-compose file in a production environment. 

# OTRS
 - Is based on https://github.com/complemento/docker.otrs
 - Backend Login: http://localhost:8090/otrs/
 - Username: root@localhost, Password: ligero


# osTicket
 - Login in Backend: http://localhost:8080/scp/login.php
 - Username: ostadmin, Password: Admin1

# Installation guide
## Windows
:warning: **Docker Desktop for Windows uses Hyper-V which causes conflicts while running Virtual-Box simultaneously. Prefere running docker in a Virtual-Box Linux instead.**
 - Follow [this guide](https://docs.docker.com/docker-for-windows/install/) to install Docker Desktop.
 - Open Powershell and enter
 ```shell
git clone https://github.com/muqiuq/tbz_ticketsystem/
```
 - Change to one of the two folders (osticket or otrs)
 ```shell
cd tbz_ticketsystem/osticket
```
 - Use the command below to start the ticket system
 ```shell
docker-compose up
```
 - Wait until docker gets everything ready (can take up to 10 minutes).
 - Use Backend login url to access backend. 

### Tips:
 - You may have to create a network proxy and service first (you'll receive a warning)
 ```shell
docker network create proxy
docker network create shell
```
 - If your running VirtualBox: Install [lubuntu](https://lubuntu.net/) and then [install docker](https://docs.docker.com/engine/install/ubuntu/) and [docker-compose] (https://docs.docker.com/compose/install/).
 - You can use this command to run it in background. 
```shell
docker-compose up -d
```
 - With this command you can stop the containers.
```shell
docker-compose down
```
 - Display all currently active containers:
```shell
docker ps
```
 - Display all containers
```shell
docker container ls -a
```
 - You can then use this command to delete the containers
```shell
docker-compose rm
```
 - Data persistance is implemented by mounting two folders (data and db) within the current directory (where you ran docker-compose). **Backup this folders!**
