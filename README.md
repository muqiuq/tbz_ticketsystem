# tbz_ticketsystem

Disclaimer: Do not use these docker-compose file in a production environment. 

# osTicket
 - Login in Backend: http://localhost:8080/scp/login.php
 - Username: ostadmin, Password: Admin1

# zammad
 - See https://docs.zammad.org/en/latest/contributing/install-docker.html

# Installation guide - osticket
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

# Installation tips - zammad
 - Just enter this command to download and start a zammad container. Run the comamnd without the "-d" flag to see the output.
```shell
docker container run -ti -d --name zammad -p 80:80 zammad/zammad
```
 - You can start the stopped container using
```shell
docker container start zammad
```
 - And to stop use
 ```shell
 docker container stop zammad
 ```

# Docker Tips:
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

# Links
 - Docker Tutorial For Beginners - https://www.youtube.com/watch?v=rOTqprHv1YE
 - Learn Docker in 12 Minutes 🐳 - https://www.youtube.com/watch?v=YFl2mCHdv24
 - Docker Compose in 12 Minutes - https://www.youtube.com/watch?v=Qw9zlE3t8Ko
