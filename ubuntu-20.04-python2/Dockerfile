FROM ubuntu:20.04
RUN useradd -ms /bin/bash easybuild
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update \
&& apt install -y curl python2 python-pip-whl \
&& LMOD_VERSION=8.6.12 \
&& curl -OL https://github.com/surak/Lmod/releases/download/${LMOD_VERSION}/lmod_${LMOD_VERSION}_all.deb \
&& apt install -y ./lmod_${LMOD_VERSION}_all.deb
# debianutils provides 'which' command
RUN apt install -y bzip2 debianutils diffutils file gcc g++ git gzip libibverbs-dev openssl libssl-dev make patch sudo tar unzip xz-utils
RUN python2 -m pip install archspec==0.1.4
