FROM ubuntu:xenial
LABEL maintainer="Gary Ritzer <gwritz@gmail.com>"
LABEL version="1.0"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        clang-6.0 \
        gdb \
        libboost-all-dev \
        lldb && \
    rm -rf /var/lib/apt/lists/*

# Don't run as root
RUN groupadd -g 1001 appuser && \
    useradd -r -u 1001 -g appuser appuser
USER appuser

ENV PATH="$PATH:/usr/lib/llvm-6.0/bin"
