FROM homeassistant/home-assistant:0.106.5

RUN apk update && apk add ca-certificates && rm -rf /var/cache/apk/*

COPY opnsense-intermediate-ca.crt /usr/local/share/ca-certificates/
COPY opnsense-root-ca.crt /usr/local/share/ca-certificates/

RUN update-ca-certificates