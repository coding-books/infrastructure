FROM nginx:latest

MAINTAINER Kravtsov Yaroslav <kravtsov.yar@gmail.com>

ADD /conf/nginx.conf /etc/nginx/
ADD /conf/crm.conf /etc/nginx/sites-available/

RUN mkdir -p /etc/nginx/sites-enabled/
RUN ln -s -f /etc/nginx/sites-available/crm.conf /etc/nginx/sites-enabled/crm.conf

RUN rm -f /etc/nginx/sites-available/default
RUN rm -f /etc/nginx/conf.d/default.conf

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443