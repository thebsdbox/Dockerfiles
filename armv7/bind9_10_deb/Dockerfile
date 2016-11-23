FROM armv7/armhf-debian:latest
MAINTAINER <daniel.finneran@gmail.com>

COPY bind9_10_0.9.10-dan_armhf.deb /

RUN apt-get update -qq && \
    apt-get install -y libjson0 libxml2 openssl && \
    dpkg -i bind9_10_0.9.10-dan_armhf.deb && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt /var/lib/dpkg /var/lib/cache /var/lib/log bind9_10_0.9.10-dan_armhf.deb

EXPOSE 53

CMD ["/usr/local/sbin/named", "-g", "-c", "/etc/bind/named.conf"]

