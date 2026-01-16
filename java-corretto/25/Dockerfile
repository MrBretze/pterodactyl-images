FROM amazoncorretto:25

LABEL author="Softwarenoob" maintainer="MrBretze"
LABEL org.opencontainers.image.source="https://github.com/Software-Noob/pterodactyl-images"
LABEL org.opencontainers.image.licenses="MIT"

RUN dnf update -y \
 && dnf install -y \
      ca-certificates \
      openssl \
      git \
      tar \
      sqlite \
      fontconfig \
      freetype \
      freetype-devel \
      lsof \
      tzdata \
      iproute \
      gcc \
      gcc-c++ \
      automake \
      make \
      libtool \
      libstdc++ \
 && dnf clean all \
 && rm -rf /var/cache/dnf \
 && useradd -m -d /home/container container

ENV LC_ALL=en_US.UTF-8
ENV LANG=en_US.UTF-8
ENV LANGUAGE=en_US.UTF-8

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]
