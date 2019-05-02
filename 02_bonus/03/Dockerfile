FROM ubuntu:latest
RUN apt update && apt upgrade -y
RUN apt install openssh-server -y
RUN apt install ufw -y
RUN apt install apache2 -y
RUN apt install vim -y
ENTRYPOINT vim /var/www/html/index.html
