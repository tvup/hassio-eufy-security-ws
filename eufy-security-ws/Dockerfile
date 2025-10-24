ARG BUILD_FROM
FROM ${BUILD_FROM:-ghcr.io/home-assistant/amd64-base:3.20}

WORKDIR /usr/src/app

RUN \
    set -x \
    && apk add --no-cache --repository=http://dl-cdn.alpinelinux.org/alpine/edge/main \
    nodejs \
    npm \
    jq \
    git

RUN npm install -g typescript@5.8.3

RUN npm install --force \
    "github:tvup/eufy-security-ws#v1.10.12"
COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]