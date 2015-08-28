# Docker Fumes #

## Containers ##
* Proxy
* Centos:7, Nginx, PHP56, Php-Fpm
* MariaDb:latest


## Install Docker ##

```
wget -qO- https://get.docker.com/ | sh
```

## install Docker-Compose ##

```
curl -L https://github.com/docker/compose/releases/download/1.4.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
```

or you can use **pip**

```
pip install -U docker-compose
```

Apply executable permissions to the binary

```
chmod +x /usr/local/bin/docker-compose
```
## To Run ##

### if you want to build a container. Not necessary. ###

```
docker build -tq jorgeben/fumes containers/fumes
```

### start ###

First time

```
docker-compose build
```

Up machines
```
docker-compose up -d
```

Stop
```
docker-compose stop
docker-compose rm
```
## To Run Mysql Client ##

```
mysql -uroot -proot -hdatabase.dev
```