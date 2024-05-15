FROM centos:7.9.2009
RUN useradd -ms /bin/bash easybuild
RUN yum -y install epel-release && yum -y install python python2-pip Lmod
RUN yum -y install bzip2 curl diffutils file gcc-c++ git gzip make openssl openssl-devel rdma-core-devel patch sudo tar unzip which xz
RUN yum -y update ca-certificates
# In order to install archspec we need to upgrade pip to latest version for Python 2
RUN python -m pip install --trusted-host pypi.python.org --trusted-host files.pythonhosted.org --trusted-host pypi.org --upgrade 'pip<21' && python -m pip install archspec
