FROM nginx:alpine

MAINTAINER Shrimp Liu <liu.shrimp@gmail.com>

ADD nginx.conf /etc/nginx/

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/' /etc/apk/repositories

ARG PUID=1000

ENV PUID ${PUID}

RUN apk update && \
    apk upgrade && \
    apk add --no-cache bash && \
    adduser -D -H -u ${PUID} -s /bin/bash www-data && \
    rm /etc/nginx/conf.d/default.conf

CMD ["nginx"]

EXPOSE 80 443