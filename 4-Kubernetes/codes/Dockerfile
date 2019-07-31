FROM ubuntu:16.04

MAINTAINER Semil Jain

RUN apt-get update -y \
    && apt-get install -y nginx \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && echo "daemon off;" >> /etc/nginx/nginx.conf

ADD index.sh ./index.sh
ADD default /etc/nginx/sites-available/default

EXPOSE 80
CMD bash index.sh && cp index.html /usr/share/nginx/html/index.html && service nginx start

