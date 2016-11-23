#DockerFile to build Infrakit

FROM goarm:latest
MAINTAINER <daniel.jam.finneran@hpe.com>

RUN export PATH=/usr/local/go/bin:$PATH
RUN mkdir -p /root/go
RUN export GOPATH=/root/go
RUN export PATH=$GOPATH/bin:$PATH
RUN mkdir -p /root/go/src/github.com/docker
WORKDIR /root/go/src/github.com/docker

RUN apt-get update -qq && \
    apt-get install -y git make && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt /var/lib/dpkg /var/lib/cache /var/lib/log

RUN git clone https://github.com/docker/infrakit.git
WORKDIR /root/go/src/github.com/docker/infrakit
# Had to re-specify the path AGAIN (bug?)
RUN export GOPATH=/root/go; make binaries
