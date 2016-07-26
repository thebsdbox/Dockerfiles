FROM armv7/armhf-debian:latest
MAINTAINER <daniel.jam.finneran@hpe.com>

RUN echo "deb http://ftp.de.debian.org/debian stretch main" >> /etc/apt/sources.list

RUN apt-get update

RUN apt-get upgrade

RUN apt-get install -y bind9

EXPOSE 53

CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]

