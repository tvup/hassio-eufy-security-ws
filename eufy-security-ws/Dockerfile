ARG BUILD_FROM
FROM ${BUILD_FROM:-ghcr.io/home-assistant/amd64-base:3.20}

WORKDIR /usr/src/app

RUN \
    set -x \
    && apk add --no-cache \
    nodejs \
    npm \
    jq \
    git

RUN npm install -g typescript@5.8.3

RUN npm install --force \
    "github:tvup/eufy-security-ws#v1.10.11"
COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]