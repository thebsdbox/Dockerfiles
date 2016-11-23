# Dockerfile to build an IncludeOS Image

FROM debian:jessie

RUN apt-get update -qq && \
    apt-get install -y git build-essential make nasm texinfo clang-3.8 cmake ninja-build subversion zlib1g-dev libtinfo-dev sudo && \
    apt-get clean autoclean && \
    apt-get autoremove -y 

RUN git clone https://github.com/hioa-cs/IncludeOS 
WORKDIR /IncludeOS
RUN ./install.sh
