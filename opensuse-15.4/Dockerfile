FROM opensuse/leap:15.4
RUN zypper --non-interactive install python3 python3-pip lua-lmod
RUN zypper --non-interactive install bzip2 curl diffutils file gcc-c++ git gzip make openssl rdma-core patch tar unzip which xz
RUN python3 -m pip install archspec
