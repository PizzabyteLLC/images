FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/graalvm/graalvm-ce:java17

LABEL       author="Garrett Summerfield" maintainer="garrett@pizzabyte.net"

RUN         microdnf update \
            && microdnf install -y curl ca-certificates openssl git tar sqlite fontconfig tzdata iproute gcc gcc-c++ freetype libstdc++ lsof glibc-locale-source glibc-langpack-en \
            && microdnf clean all

## Setup user and working directory
RUN         adduser --home-dir /home/container container
USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

STOPSIGNAL SIGINT

COPY        --chown=container:container ./../../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh"]
