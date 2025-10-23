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
RUN npm install --force \
    "github:tvup/eufy-security-ws#40f568b"
COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]
