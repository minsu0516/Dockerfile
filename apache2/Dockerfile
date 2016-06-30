FROM ubuntu:14.04
MAINTAINER mskim <minsu0516@gmail.com>

 RUN echo "deb http://ftp.daum.net/ubuntu trusty main" > /etc/apt/sources.list
 RUN echo "deb http://ftp.daum.net/ubuntu trusty-updates main" >> etc/apt/sources.list
 RUN echo "deb http://ftp.daum.net/ubuntu trusty-security main" >> etc/apt/sources.list
 RUN echo "deb http://ftp.daum.net/ubuntu trusty universe" >> etc/apt/sources.list
 RUN echo "deb http://ftp.daum.net/ubuntu trusty-updates universe" >> etc/apt/sources.list
 
# Avoid ERROR: invoke-rc.d: policy-rc.d denied execution of start.
RUN echo "#!/bin/sh\nexit 0" > /usr/sbin/policy-rc.d

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get -yq install \
        curl \
        apache2 && \
        rm -rf /var/lib/apt/lists/*

RUN a2enmod proxy_http proxy_ajp proxy_balancer rewrite headers

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf
ADD vhost-default.conf /etc/apache2/sites-available/default

RUN mkdir /app 
RUN mkdir /conf

ADD run.sh /run.sh
ADD index.html /app/
ADD proxy.conf /conf

RUN chmod 755 /*.sh

EXPOSE 80
EXPOSE 433

WORKDIR /app


CMD ["/run.sh"]