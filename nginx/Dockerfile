FROM nginx:alpine

MAINTAINER Shrimp Liu <liu.shrimp@gmail.com>

ADD nginx.conf /etc/nginx/

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/' /etc/apk/repositories

ARG PUID=1000
ARG PGID=1000

ENV PUID ${PUID}
ENV PGID ${PGID}

RUN apk update && \
    apk upgrade && \
    apk add --no-cache bash && \
    addgroup -g ${PGID} www-data  && \
    adduser -D -H -u ${PUID} -G www-data -s /bin/bash www-data && \
    rm /etc/nginx/conf.d/default.conf

CMD ["nginx"]

EXPOSE 80 443