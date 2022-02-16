FROM rockylinux/rockylinux:8.5
# enable PowerTools repository, required by Lmod in EPEL
RUN dnf -y install dnf-plugins-core && dnf config-manager --set-enabled powertools \
&& dnf -y install epel-release && dnf -y install python3 Lmod
