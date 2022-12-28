FROM python:3.10-alpine

# Dokerfile's infos
LABEL maintainer="nekoserv" mail="nekoserv@fai.tld"
LABEL description="Alpine + python3 + transmission"
LABEL website="https://github.com/TODO/docker-transmission"
LABEL version="1.0"

# init
ARG UID
ARG GID

# install
RUN addgroup -g $GID tbt && \
    adduser -S -u $UID -G tbt tbt && \
    apk add --no-cache transmission-daemon tzdata

# drop privileges
USER tbt

# run!
ENTRYPOINT ["/usr/bin/transmission-daemon", "-f"]
