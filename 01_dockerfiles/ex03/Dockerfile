FROM ubuntu:16.04
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y curl openssh-server ca-certificates
RUN apt install -y tzdata
RUN apt-get install git-core -y
EXPOSE 443 80 22
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt-get -y install gitlab-ce
RUN apt-get clean && rm -rf /var/lib/apt/lists/ */tmp/* /var/tmp/*
RUN echo "sed -i \"/external_url 'http/c\external_url 'https://10.11.2.3'\" /etc/gitlab/gitlab.rb " > script.sh
RUN echo "service ssh start" >> script.sh
RUN echo "(/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null" >> script.sh
ENTRYPOINT sh script.sh
#docker run --name git -p 80:80 -p 443:443 -p 10.11.2.3:22:22 mygitlab
