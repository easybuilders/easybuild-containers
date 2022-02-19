FROM ubuntu:20.04
RUN apt update \
&& apt install -y curl python3 python3-distutils \
&& curl -OL https://github.com/surak/Lmod/releases/download/8.6.12/lmod_8.6.12_all.deb \
&& apt remove -y --purge curl \
&& apt install -y ./lmod_8.6.12_all.deb
