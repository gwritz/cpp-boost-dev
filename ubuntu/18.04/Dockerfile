FROM ubuntu:bionic
LABEL maintainer="Gary Ritzer <gwritz@gmail.com>"
LABEL version="1.0"

RUN apt-get update && apt-get install -y clang-6.0 libboost-all-dev gdb lldb

RUN groupadd -g 999 appuser && useradd -r -u 999 -g appuser appuser
USER appuser

ENV PATH="$PATH:/usr/lib/llvm-6.0/bin"
