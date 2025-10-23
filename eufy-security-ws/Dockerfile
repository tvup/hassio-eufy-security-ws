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
RUN git clone https://github.com/tvup/eufy-security-ws.git . \
    && npm install \
    && cd node_modules/eufy-security-client \
    && npm install \
    && cd ../.. \
    && npm run build
COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]
