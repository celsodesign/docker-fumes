## lcfumes/docker ##

### Containers ###
Proxy

Centos:7, Nginx, PHP5.6, Php-Fpm

MariaDb:10.0


This project was made to use with composer.json. To run it alone, you need do change some configurations in the file docker-compose.yml. 
If you wanna run it alone, you can write me. It will be a pleasure to help you.

### Using in composer.json ###

```
"repositories": [
    {
      "url": "git@github.com:lcfumes/docker-fumes.git",
      "type": "git"
    }
],
"require-dev": {
    "lcfumes/docker": "dev-master"
}
```

### Runing Composer ###

Local Machine:

```
composer install
```

Live Machine

```
composer install --no-dev
```

### About the project ###

You need to create a tmp folder, with write permission.

```
cd /project/
mkdir tmp/
mkdir tmp/nginx
chmod -R 777 tmp
```

This project was made to run in the ZendFramework. If you use another framework, my sugestion is to create a simbolic link called "public". Example in Silex Framework.
```
cd /project/
ln -s web public
```

### Install Docker ###

```
wget -qO- https://get.docker.com/ | sh
```

###  Install Docker-Compose ###

```
curl -L https://github.com/docker/compose/releases/download/1.4.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
```

or you can use pip

```
pip install -U docker-compose
```

Apply executable permissions to the binary

```
chmod +x /usr/local/bin/docker-compose
```

## To Run ##

### Up machines ###

```
cd /yourproject/vendor/lcfumes/docker/
docker-compose up -d
```

### Stop ###

```
docker-compose stop
docker-compose rm
```

### Database ###

```
mysql -uroot -proot -hdatabase.dev
```

### Browser ###

```
http://webproject.dev
```

### Docker HUB ###

This project use the images from Docker Hub

lcfumes/nginx-php56 - https://hub.docker.com/r/lcfumes/nginx-php56/

jwilder/nginx-proxy - https://hub.docker.com/r/jwilder/nginx-proxy/

mariadb - https://hub.docker.com/_/mariadb/
