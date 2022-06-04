FROM centos:8.4.2105
RUN useradd -ms /bin/bash easybuild
# fix "Failed to download metadata" issue, because CentOS 8 reached EOL
# see https://techglimpse.com/failed-metadata-repo-appstream-centos-8
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* \
&& sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* \
&& for repo in `ls /etc/yum.repos.d/CentOS-*`; do echo $repo; echo "timeout=3600" >> $repo; done \
# note: this also results in updating to CentOS 8.5.2111 (final 8.5 release)
&& dnf -y update \
# enable PowerTools repository, required by Lmod in EPEL
&& dnf -y install dnf-plugins-core && dnf config-manager --set-enabled powertools \
&& dnf -y install epel-release && dnf -y install python3 Lmod
RUN dnf -y install bzip2 curl diffutils file gcc-c++ git gzip make openssl openssl-devel rdma-core-devel patch tar unzip which xz
RUN python3 -m pip install archspec
