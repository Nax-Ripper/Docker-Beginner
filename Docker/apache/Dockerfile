
FROM ubuntu:latest

WORKDIR /app

RUN  apt update -y

RUN  apt-get install apache2 -y

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

RUN service apache2 restart

EXPOSE 80

CMD ["apache2ctl", "-D", "FOREGROUND"]

