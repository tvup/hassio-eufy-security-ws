ARG BUILD_FROM
FROM $BUILD_FROM

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
    "github:tvup/eufy-security-ws#v1.10.3"
COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]