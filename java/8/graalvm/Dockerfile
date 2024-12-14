FROM        --platform=$TARGETOS/$TARGETARCH ubuntu:24.04

LABEL       author="Garrett Summerfield" maintainer="garrett@pizzabyte.net"

ARG         TARGETPLATFORM

RUN         apt update -y \
            && apt install -y \
                curl \
                lsof \
                ca-certificates \
                openssl \
                git \
                tar \
                sqlite3 \
                fontconfig \
                tzdata \
                iproute2 \
                libfreetype6 \
                tini \
                zip \
                unzip \
                libstdc++6

# Install GraalVM
RUN         case ${TARGETPLATFORM} in \
                "linux/amd64")  ARCH=amd64  ;; \
                "linux/arm64")  ARCH=aarch64  ;; \
            && esac \
            && curl -sL https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-21.2.0/graalvm-ce-java8-linux-${ARCH}-21.2.0.tar.gz -o graalvm.tar.gz; \
            && tar -xzf graalvm.tar.gz -C /opt \
            && rm graalvm.tar.gz \
            && mv /opt/graalvm-ce-java8-21.2.0 /opt/graalvm

ENV         PATH="/opt/graalvm/bin:$PATH"
ENV         JAVA_HOME="/opt/graalvm"

## Setup user and working directory
RUN         useradd -m -d /home/container -s /bin/bash container
USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

STOPSIGNAL SIGINT

COPY        --chown=container:container ./../../entrypoint.sh /entrypoint.sh
RUN         chmod +x /entrypoint.sh
ENTRYPOINT    ["/usr/bin/tini", "-g", "--"]
CMD         ["/entrypoint.sh"]
