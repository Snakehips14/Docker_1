FROM ubuntu

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

RUN apt-get update -y && apt-get upgrade -y && \
	apt-get install -y software-properties-common python3.7 vim git

EXPOSE 80

CMD bash

# build : docker build -t python_env .
# run : docker run -it --rm -p 80 python_env
