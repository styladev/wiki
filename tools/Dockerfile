# doesn't have version tags!
FROM requarks/wiki:latest

ARG ENVIRONMENT=stage

WORKDIR /var/wiki

# github deploy private key
COPY wikijs.prv wikijs.prv

COPY config.$ENVIRONMENT.yml config.yml

EXPOSE 3000
ENTRYPOINT [ "node", "server" ]
