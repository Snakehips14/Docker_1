FROM debian

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

RUN apt-get update -y && apt-get upgrade -y && \
	apt-get install -y telnet

EXPOSE 8000

CMD telnet towel.blinkenlights.nl

# build : docker build -t "star_wars" .
# run : docker run -it --rm -p 8000 star_wars
# quit : ctrl + ]
