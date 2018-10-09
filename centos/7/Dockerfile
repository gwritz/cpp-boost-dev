FROM centos:7
LABEL maintainer="Gary Ritzer <gwritz@gmail.com>"
LABEL version="1.0"

# Install g++ capable of c++ 11 (the best we can do right now)
RUN yum install -y centos-release-scl && \
    yum-config-manager --enable rhel-server-rhscl-7-rpms && \
    yum install -y \
        boost-devel \
        boost-static \
        clang \
        clang-devel \
        clang-analyzer \
        llvm-static \
        llvm-toolset-7-clang \
        llvm-toolset-7-clang-devel \
        llvm-toolset-7-clang-libs \
        llvm-toolset-7-clang-tools-extra \
        llvm-toolset-7-git-clang-format \
        llvm-toolset-7-clang-analyzer \
        llvm-toolset-7-libomp.x86_64 \
        devtoolset-7 \
        binutils-devel \
        gcc \
        gdb \
        glibc-devel \
        glibc-static \
        lldb && \
    yum clean all -y

RUN groupadd -g 1001 appuser && useradd -r -u 1001 -g appuser appuser
USER appuser

ADD entrypoint.sh /
ENTRYPOINT [ "/entrypoint.sh" ]
