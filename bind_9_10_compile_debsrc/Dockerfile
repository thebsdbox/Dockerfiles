FROM armv7/armhf-debian:latest
MAINTAINER <daniel.jam.finneran@hpe.com>

RUN echo "deb-src http://ftp.de.debian.org/debian stretch main" >> /etc/apt/sources.list

RUN apt-get update
RUN apt-get install -y dpkg-dev libjson-c-dev devscripts

RUN apt-get source bind9
RUN apt-get build-dep -y bind9

WORKDIR /bind9-9.10.3.dfsg.P4

RUN debuild -b -uc -us

EXPOSE 53

CMD ["/usr/local/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]

