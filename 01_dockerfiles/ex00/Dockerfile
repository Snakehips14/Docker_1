FROM alpine

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

RUN apk update && \
	apk upgrade && \
	apk add vim

ENTRYPOINT ["vim"]

# buid : docker build -t "ex00" .
# run : docker run --rm -ti ex00
