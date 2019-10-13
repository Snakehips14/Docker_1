FROM ubuntu

MAINTAINER behiraux <benjamin.hiraux@gmail.com>

# Exposer les ports 27017 (MongoDB), 3000 (Node.js/express.js), et 4200 (Angular)
EXPOSE 3000 27017 4200

# Installer les packages essentiels
RUN apt-get update -y && apt-get upgrade -y && \
	apt-get install -y git curl ssh gcc make build-essential sudo apt-utils && \
	apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Installer Node.js
RUN	curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash - && \
	apt-get install -y nodejs && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Installer Yarn puis Angular et Express.js
RUN	npm install -g yarn && \
	npm install --quiet -g @angular/cli && \
	npm install -g express-generator && \
	npm cache clean --force

# build : - docker pull mongo
#		  - docker run -p 27017:27017 -d --name db mongo
#		  - docker build -t "fullmean_stack" .
# run : docker run -it --rm -p 3000 -p 4200 --name fullmean_stack --link db:db fullmean_stack
# usage : node -v, express --version, ng --version
