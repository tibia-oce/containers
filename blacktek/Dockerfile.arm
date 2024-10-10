FROM ubuntu:22.04

ENV VCPKG_FORCE_SYSTEM_BINARIES=1
ENV VCPKG_ROOT=/bts/vcpkg

RUN apt update && apt install -y \
    unzip \
    make \
    g++ \
    uuid-dev \
    wget \
    curl \
    zip \
    tar \
    git \
    pkg-config \
    cmake \
    ninja-build \
    python3

RUN mkdir /bts && cd /bts/ && wget https://github.com/premake/premake-core/archive/refs/heads/master.zip && \
    unzip master.zip && rm master.zip && \
    cd /bts/premake-core-master && make -f Bootstrap.mak linux && \
    mv /bts/premake-core-master/bin/release/premake5 /bin/premake5

RUN cd /bts && git clone https://github.com/microsoft/vcpkg.git && \
    /bts/vcpkg/bootstrap-vcpkg.sh

COPY vcpkg.json /usr/src/bts/
WORKDIR /usr/src/bts
RUN apt install -y pkg-config
RUN cd /usr/src/bts && /bts/vcpkg/vcpkg install
