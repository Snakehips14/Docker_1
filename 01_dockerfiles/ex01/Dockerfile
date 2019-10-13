FROM debian:latest

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -y && apt-get upgrade -y && apt-get install wget -y && apt-get install bzip2 -y

RUN useradd teamspeak
CMD /home/teamspeak

RUN wget http://dl.4players.de/ts/releases/3.7.0/teamspeak3-server_linux_amd64-3.7.0.tar.bz2
RUN tar xvfj teamspeak3-server_linux_amd64-3.7.0.tar.bz2

RUN apt-get remove bzip2 wget -y && rm -rf teamspeak3-server_linux_amd64-3.7.0.tar.bz2

EXPOSE 9987/udp 10011 30033 41144

WORKDIR teamspeak3-server_linux_amd64
COPY ts3server.ini /home/teamspeak/teamspeak3-server_linux_amd64/ts3server.ini

USER teamspeak

ENTRYPOINT [ "sh" , "ts3server_minimal_runscript.sh", "inifile=ts3server.ini" ]

# build : docker build -t "ex01" .
# run : docker run --rm -ti -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -e TS3SERVER_LICENSE=accept ex01
# usage :	=> Aller sur le client ts3 dans puis mettre l'ip de Char le login et le password dnas les champs dispos, puis le token.
