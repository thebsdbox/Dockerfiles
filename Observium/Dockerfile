FROM armv7/armhf-debian:latest
MAINTAINER <daniel.jam.finneran@hpe.com>

RUN apt-get update
RUN apt-get -y install libapache2-mod-php5 \
php5-cli php5-mysql php5-gd \
php5-mcrypt php5-json \
php-pear snmp fping \
python-mysqldb \
rrdtool subversion whois \
mtr-tiny ipmitool \
graphviz imagemagick

RUN mkdir -p /opt/observium
