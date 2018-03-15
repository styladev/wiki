FROM node:8-alpine

ARG ENV=localdocker

RUN apk update && \
    apk add bash curl git openssh supervisor --no-cache && \
    mkdir -p /var/wiki && \
    mkdir -p /logs

WORKDIR /var/wiki

COPY . /var/wiki

RUN yarn install

COPY tools/config.$ENV.yml /var/wiki/config.yml
COPY tools/wikijs.prv /var/wiki/wikijs.prv
RUN chmod 600 wikijs.prv

ENV WIKI_JS_HEROKU=1
ENV WIKI_ADMIN_EMAIL admin@styla.com

EXPOSE 3000

CMD ["yarn", "run", "dev"]
