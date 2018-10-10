FROM ubuntu:bionic
LABEL maintainer="Gary Ritzer <gwritz@gmail.com>"
LABEL version="1.0"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        ca-certificates \
        clang-6.0 \
        gdb \
        libboost-all-dev \
        lldb \
        make \
        ninja-build \
        wget && \
    mkdir -p /tmp/cmake && \
    cd /tmp/cmake && \
    wget https://cmake.org/files/v3.12/cmake-3.12.3-Linux-x86_64.sh && \
    sh cmake-3.12.3-Linux-x86_64.sh --prefix=/usr/local --exclude-subdir && \
    cd / && \
    rm -rf /tmp/cmake && \
    apt-get remove -y wget && \
    rm -rf /var/lib/apt/lists/*

# Don't run as root
RUN groupadd -g 1001 appuser && \
    useradd -r -u 1001 -g appuser appuser
USER appuser

ENV PATH="$PATH:/usr/lib/llvm-6.0/bin"
