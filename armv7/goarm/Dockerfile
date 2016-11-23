FROM armv7/armhf-debian:latest
MAINTAINER <daniel.finneran@gmail.com>

COPY go1.7.3.linux-armv6l.tar.gz /

RUN tar -C /usr/local/ -xzf go1.7.3.linux-armv6l.tar.gz

RUN rm /go1.7.3.linux-armv6l.tar.gz

ENV PATH=$PATH:/usr/local/go/bin
