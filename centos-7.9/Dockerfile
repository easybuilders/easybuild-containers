FROM centos:7.9.2009
RUN yum -y install epel-release && yum -y install python python2-pip Lmod
RUN yum -y install bzip2 curl diffutils file gcc-c++ git gzip make openssl-devel rdma-core-devel patch tar unzip which xz
RUN yum -y update ca-certificates
RUN python -m pip install archspec
