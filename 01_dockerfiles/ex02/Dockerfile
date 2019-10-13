FROM ruby

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

RUN apt-get update -y && apt-get upgrade -y && \
    apt-get install sqlite3 nodejs gem rails -y 

ADD app/ /opt/app

ONBUILD WORKDIR /opt/app/

ONBUILD RUN bundle install \
	    && rails db:migrate db:seed

# Build Dockerfile : docker build -t ft-rails:on-build .

# Build Dockerfile-son : docker build -f Dockerfile-son -t ex02 .

# Run container : docker run -p 3000:3000 ex02
