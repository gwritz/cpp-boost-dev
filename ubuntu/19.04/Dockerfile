FROM ubuntu:disco
LABEL maintainer="Gary Ritzer <gwritz@gmail.com>"
LABEL version="1.0"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        ca-certificates \
        clang-8 \
        gdb \
        g++ \
        libboost-all-dev \
        lldb \
        make \
        ninja-build \
        cmake && \
    rm -rf /var/lib/apt/lists/*

# Don't run as root
RUN groupadd -g 1001 appuser && \
    useradd -r -u 1001 -g appuser appuser
USER appuser

ENV PATH="$PATH:/usr/lib/llvm-8/bin"
