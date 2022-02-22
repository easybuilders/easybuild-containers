FROM rockylinux/rockylinux:8.5
# enable PowerTools repository, required by Lmod in EPEL
RUN dnf -y install dnf-plugins-core && dnf config-manager --set-enabled powertools \
&& dnf -y install epel-release && dnf -y install python3 Lmod
RUN dnf -y install bzip2 curl diffutils file gcc-c++ git gzip make openssl-devel rdma-core-devel patch tar unzip which xz
RUN python3 -m pip install archspec
