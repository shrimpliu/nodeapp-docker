FROM node:9.7

MAINTAINER Shrimp Liu <liu.shrimp@gmail.com>

ARG PUID=1000
ARG PGID=1000

ENV PUID ${PUID}
ENV PGID ${PGID}

RUN usermod -u ${PUID} node
RUN groupmod -g ${PGID} node

WORKDIR /var/www

RUN npm install --production

CMD npm start src/