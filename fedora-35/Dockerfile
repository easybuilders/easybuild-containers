FROM fedora:35
# enable PowerTools repository, required by Lmod in EPEL
RUN dnf -y install dnf-plugins-core && dnf config-manager --set-enabled powertools \
&& dnf -y install epel-release && dnf -y install python3 Lmod
RUN dnf -y install bzip2 file gcc-c++ git gzip make openssl-devel rdma-core-devel patch tar unzip xz
