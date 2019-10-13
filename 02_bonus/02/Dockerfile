FROM ubuntu

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

RUN apt-get update -y && apt-get install -y && \
    apt-get install nano wget dialog net-tools nginx -y

WORKDIR /etc/nginx

EXPOSE 80

CMD ["nginx"]

# build : docker build -t "nginx_server" .
# run : docker run -d -p 8080:80 nginx_server
