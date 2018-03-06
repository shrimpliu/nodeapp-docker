FROM redis:4.0

MAINTAINER Shrimp Liu <liu.shrimp@gmail.com>

VOLUME /data

ARG PUID=1000
ARG PGID=1000

ENV PUID ${PUID}
ENV PGID ${PGID}

ARG REDIS_PASSWORD=test

ENV REDIS_PASSWORD ${REDIS_PASSWORD}

RUN usermod -u ${PUID} redis
RUN groupmod -g ${PGID} redis

EXPOSE 6379

CMD [ "sh", "-c", "redis-server --requirepass ${REDIS_PASSWORD}" ]