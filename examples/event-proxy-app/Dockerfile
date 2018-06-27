FROM node:9-stretch

RUN apt-get update && apt-get install -y git-core curl python build-essential

RUN yarn global add typescript@^2.7.1

ADD . /opt/orbs

WORKDIR /opt/orbs

RUN ./build.sh

CMD node dist/index.js
