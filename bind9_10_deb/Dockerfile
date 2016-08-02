FROM armv7/armhf-debian:latest
MAINTAINER <daniel.finneran@gmail.com>

RUN apt-get update
RUN apt-get install -y libjson0 libxml2 openssl

COPY bind9_10_0.9.10-dan_armhf.deb /

RUN dpkg -i bind9_10_0.9.10-dan_armhf.deb

EXPOSE 53

CMD ["/usr/local/sbin/named", "-g", "-c", "/etc/bind/named.conf"]

