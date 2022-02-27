FROM opensuse/leap:15.4
RUN zypper --non-interactive install python3 python3-pip lua-lmod
# glibc-locale provides locale stuff, required for example by libxml2 test suite
RUN zypper --non-interactive install bzip2 curl diffutils file gcc-c++ git glibc-locale gzip libopenssl-devel make rdma-core-devel patch tar unzip which xz
RUN python3 -m pip install archspec
