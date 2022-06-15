FROM rust:1.59.0

LABEL maintainer="Adam Baca <baca.adamv@gmail.com>"

ARG DEBIAN_FRONTEND=noninteractive
ARG USER=me
ARG HOME=/home/$USER

###### DEPENDENCY MANAGEMENT #####
RUN apt -y update && \
    apt install --yes --no-install-recommends \
        sudo \
        nano \
        zip \
        cifs-utils \
        htop
RUN adduser --disabled-password --gecos '' ${USER}
RUN adduser ${USER} sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER ${USER}
WORKDIR ${HOME}
