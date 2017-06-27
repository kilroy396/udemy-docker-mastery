# https://hub.docker.com/_/node/
FROM node:6-alpine

RUN apk add --update tini \
        && mkdir -p /usr/src/app 

WORKDIR /usr/src/app

COPY . . 

RUN npm install \
        && npm cache clean --force 

EXPOSE 3000
# expose these ports on the docker virtual network
# you still need to use -p or -P to open/forward these ports on host

CMD ["tini", "--", "node", "./bin/www"]
# required: run this command when container is launched
# only one CMD allowed, so if there are mulitple, last one wins
