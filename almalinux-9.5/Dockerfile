FROM almalinux:9.5
RUN useradd -ms /bin/bash easybuild
RUN dnf -y update \
# enable crb repository
&& dnf -y install dnf-plugins-core && dnf config-manager --set-enabled crb \
&& dnf -y install epel-release && dnf -y install python3 python3-pip Lmod
# --allowerasing is required to allow to install curl and remove conflicting curl-minimal which is part of the base image
# glibc-langpack-en provides locale stuff (for en_US.UTF-8)
RUN dnf -y --allowerasing install bzip2 curl diffutils file findutils gcc-c++ git glibc-langpack-en gzip make openssl openssl-devel rdma-core-devel patch sudo tar unzip which xz
# install requirements to build OpenSSL 1.1 and 3.0 from source
RUN dnf -y install perl-FindBin perl-File-Compare perl-File-Copy perl-IPC-Cmd perl-Pod-Html
RUN python3 -m pip install archspec
