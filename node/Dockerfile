FROM node:9.7

MAINTAINER Shrimp Liu <liu.shrimp@gmail.com>

WORKDIR /var/www

RUN npm install -g pm2

CMD npm install --production && pm2-runtime start src/ --watch -i 2