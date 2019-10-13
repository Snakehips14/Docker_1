FROM ubuntu

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

RUN	apt-get update -y && apt-get upgrade -y && \
	apt-get install -y ca-certificates openssh-server wget postfix

RUN	wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod 777 script.deb.sh && ./script.deb.sh && \
	apt-get install -y gitlab-ce && \
	apt update && apt install -y tzdata && \
	apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# build : docker build -t "ex03" .
# run : docker run --rm -it -p 8443:443 -p 8080:80 -p 8022:22 --privileged ex03
# usage :	=> dans le navigateur "https://192.168.99.100:8080"
#		=> en HTTPS : git clone http://192.168.99.100:8080/root/docker.git/ docker
#		=> en SSH : doocker-machine ssh Char puis git clone http://192.168.99.100:8080/root/docker.git/ docker
