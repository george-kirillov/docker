FROM ubuntu:bionic

LABEL maintainer="georgekirillov89@gmail.com"

ENV USERNAME=freedom
ENV PASSWORD=Qwerty123

RUN set -xe \
    && apt-get update \
    && apt-get install -y dante-server \
    && rm -rf /var/lib/apt/lists/* \
    && useradd -s /bin/bash $USERNAME \
    && printf '$PASSWORD\n$PASSWORD\n' | passwd $USERNAME

ADD dante.conf /etc/dante.conf

EXPOSE 1920/tcp
EXPOSE 1920/udp

CMD danted
