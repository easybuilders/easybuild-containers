FROM centos:7.9.2009
RUN useradd -ms /bin/bash easybuild
# mirrorlist.centos.org doesn't exists anymore, update repo files
RUN sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/CentOS-*.repo \
  && sed -i s/^#.*baseurl=http/baseurl=http/g /etc/yum.repos.d/CentOS-*.repo \
  && sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/CentOS-*.repo
RUN yum -y install epel-release && yum -y install python3 python3-pip Lmod
RUN yum -y install bzip2 curl diffutils file gcc-c++ git gzip make openssl openssl-devel rdma-core-devel patch sudo tar unzip which xz
RUN yum -y update ca-certificates
RUN python3 -m pip install archspec
