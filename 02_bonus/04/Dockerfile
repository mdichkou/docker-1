FROM ubuntu:latest
RUN apt update && apt upgrade -y
RUN apt-get install software-properties-common -y
RUN apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
RUN add-apt-repository 'deb [arch=amd64] http://mirror.zol.co.zw/mariadb/repo/10.3/ubuntu bionic main'
RUN DEBIAN_FRONTEND=noninteractive apt-get install mariadb-server mariadb-client -y
