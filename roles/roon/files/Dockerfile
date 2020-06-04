FROM debian:buster-slim
RUN apt-get update \
        && apt-get -y install --no-install-recommends bash curl bzip2 ffmpeg cifs-utils alsa-utils && apt-get autoremove -y && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN curl -O http://download.roonlabs.com/builds/RoonServer_linuxx64.tar.bz2
RUN tar xf RoonServer_linuxx64.tar.bz2

ENV ROON_DATAROOT=/var/roon

ENTRYPOINT /RoonServer/start.sh