FROM centos:7.9.2009
RUN useradd -ms /bin/bash easybuild
RUN yum -y install epel-release && yum -y install python3 python3-pip Lmod
RUN yum -y install bzip2 curl diffutils file gcc-c++ git gzip make openssl openssl-devel rdma-core-devel patch sudo tar unzip which xz
RUN yum -y update ca-certificates
RUN python3 -m pip install archspec
