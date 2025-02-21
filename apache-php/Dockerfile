FROM newdeveloper/apache-php

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install nano -y
RUN apt-get install tzdata -y 
# RUN tzdata ENV TZ "America/Caracas"

RUN apt-get install git curl apache2 php libapache2-mod-php php-mysql php-xml php-zip php-gd -y

RUN rm -rf /var/www/html/* 
ADD ./apache-php/html /var/www/html 

RUN rm -f /etc/apache2/sites-available/000-default.conf 
ADD ./apache-php/vhost/000-default.conf /etc/apache2/sites-available/
RUN echo "Mutex posixsem" >> /etc/apache2/apache2.conf

RUN a2enmod proxy
RUN a2enmod proxy_balancer
RUN a2enmod proxy_http
RUN a2enmod rewrite
RUN a2enmod ssl
RUN a2enmod headers
RUN a2enmod proxy_html
RUN a2enmod lbmethod_byrequests
RUN chown -R www-data:www-data /var/www/html/

ENV APACHE_RUN_USER www-data 
ENV APACHE_RUN_GROUP www-data 
ENV APACHE_LOG_DIR /var/log/apache2 
ENV APACHE_LOCK_DIR /var/lock/apache2 
ENV APACHE_PID_FILE /var/run/apache2.pid

EXPOSE 80

CMD [ "apachectl", "-DFOREGROUND" ]