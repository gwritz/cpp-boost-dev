FROM centos:6
LABEL maintainer="Gary Ritzer <gwritz@gmail.com>"
LABEL version="1.0"

# Add repo for clang
ADD llvm.repo /etc/yum.repos.d/

RUN yum install -y centos-release-scl
RUN yum install -y devtoolset-7 \
        boost-devel \
        boost-static \
        clang \
        clang-devel

RUN yum install -y glibc-static \
        lld \
        lldb \
        libc++ \
        libc++abi \
        libc++-devel \
        libstdc++ \
        libstdc++-devel \
        devtoolset-7-libstdc++-devel


# RUN yum install -y libstdc++-devel.x86_64 gdb.x86_64
# RUN yum install -y boost-devel.x86_64
# RUN yum install -y boost.x86_64 boost-devel.x86_64
# RUN yum install -y clang boost.x86_64 boost-static.x86_64 boost-devel.x86_64 gdb lldb
# RUN yum install -y clang clang-devel glibc-devel.x86_64  libc++ libc++-devel lld lldb lldb-devel llvm llvm-devel
# RUN yum install -y guile guile-devel

# RUN groupadd -g 999 appuser && useradd -r -u 999 -g appuser appuser
# USER appuser

ADD entrypoint.sh /
ENTRYPOINT [ "/entrypoint.sh" ]
CMD [ "bash" ]