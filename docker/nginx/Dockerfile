FROM node:16-alpine as node
FROM nginx:1.20-alpine
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

RUN apk update && \
    apk add --update --no-cache --virtual=.build-dependencies g++

COPY --from=node /usr/local/bin /usr/local/bin
COPY --from=node /opt /opt
COPY ./docker/nginx/*.conf /etc/nginx/conf.d/

WORKDIR /work/app   apk add --update --no-cache ==virtual=.build-dependencies g++
