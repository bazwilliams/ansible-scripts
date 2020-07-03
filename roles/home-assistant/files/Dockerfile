FROM alpine as build
RUN apk update && apk add ca-certificates && rm -rf /var/cache/apk/*
COPY opnsense-intermediate-ca.crt /usr/local/share/ca-certificates/
COPY opnsense-root-ca.crt /usr/local/share/ca-certificates/
RUN update-ca-certificates

FROM homeassistant/home-assistant:0.112.0
COPY --from=build /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/ca-certificates.crt