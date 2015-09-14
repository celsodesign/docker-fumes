FROM centos:7

MAINTAINER Luiz Fumes <lcfumes@gmail.com>

RUN yum -y update && yum clean all

ADD nginx.repo /etc/yum.repos.d/nginx.repo

RUN yum -y install nginx && yum clean all 

RUN yum -y --enablerepo=remi,remi-php56 install nginx php-fpm php-common php-pear php-pdo php-mysqlnd php-mcrypt php-mbstring php-gd php-pecl-memcache php-pecl-memcached 

RUN yum install -y python-setuptools
RUN easy_install pip
RUN pip install supervisor 

ADD nginx.conf /etc/nginx/nginx.conf
ADD web.conf /etc/nginx/conf.d/default.conf

ADD supervisord.conf /etc/

RUN sed -i "s/;date.timezone =/date.timezone = America\/Sao_Paulo/" /etc/php.ini

EXPOSE 80

CMD ["supervisord", "-n"]
