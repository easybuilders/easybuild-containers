FROM fedora:36
RUN useradd -ms /bin/bash easybuild
RUN dnf -y install python3 python3-pip Lmod
# glibc-langpack-en provides locale stuff (for en_US.UTF-8)
RUN dnf -y install bzip2 curl diffutils file gcc-c++ git glibc-langpack-en gzip make openssl openssl-devel rdma-core-devel patch sudo tar unzip which xz
RUN python3 -m pip install archspec
