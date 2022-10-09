FROM almalinux:9.0
ENV LMOD_VER 8.7
RUN useradd -ms /bin/bash easybuild
RUN dnf -y update \
# enable crb repository
&& dnf -y install dnf-plugins-core && dnf config-manager --set-enabled crb \
&& dnf -y install epel-release && dnf -y install python3 python3-pip
# --allowerasing is required to allow to install curl and remove conflicting curl-minimal which is part of the base image
RUN dnf -y --allowerasing install bzip2 curl diffutils file gcc-c++ git gzip make openssl openssl-devel rdma-core-devel patch tar unzip which xz
# install requirements to build Lmod
RUN dnf -y install procps-ng lua-filesystem lua-posix lua-devel lua tcl
# Build Lmod from source
RUN curl -LO https://sourceforge.net/projects/lmod/files/Lmod-${LMOD_VER}.tar.bz2 \
 && tar xf Lmod-${LMOD_VER}.tar.bz2 \
 && cd Lmod-${LMOD_VER} \
 && ./configure --prefix=/opt/apps --with-fastTCLInterp=no \
 && make install \
 && cd .. \
 && rm -rf Lmod-${LMOD_VER} \
 && rm -rf Lmod-${LMOD_VER}.tar.bz2 \
 && ln -s /opt/apps/lmod/lmod/init/profile /etc/profile.d/modules.sh \
 && ln -s /opt/apps/lmod/lmod/init/cshrc /etc/profile.d/modules.csh
# install requirements to build OpenSSL 1.1 and 3.0 from source
RUN dnf -y install perl-FindBin perl-File-Compare perl-File-Copy perl-IPC-Cmd perl-Pod-Html
RUN python3 -m pip install archspec
