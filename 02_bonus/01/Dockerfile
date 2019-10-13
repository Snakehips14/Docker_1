FROM ubuntu

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

RUN apt-get update -y && apt-get upgrade -y && \
	apt-get install -y nodejs npm git vim 

RUN npm install yarn --global && npm install npm --global

# build : docker build -t "node_yarn_env" .
# run : docker run -it --rm node_yarn_env
