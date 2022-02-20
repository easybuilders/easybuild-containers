FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update \
&& apt install -y curl python3 python3-distutils python3-pip \
&& LMOD_VERSION=8.6.12 \
&& curl -OL https://github.com/surak/Lmod/releases/download/${LMOD_VERSION}/lmod_${LMOD_VERSION}_all.deb \
&& apt install -y ./lmod_${LMOD_VERSION}_all.deb
RUN apt install -y bzip2 diffutils file gcc g++ git gzip libibverbs-dev libssl-dev make patch tar unzip xz-utils
RUN python3 -m pip install archspec
