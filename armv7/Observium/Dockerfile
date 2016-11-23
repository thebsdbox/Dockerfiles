FROM armv7/armhf-debian:latest
MAINTAINER <daniel.jam.finneran@hpe.com>

# Update and install the required packages, then clean

RUN apt-get update -qq && \ 
    apt-get -y install libapache2-mod-php5 \
    php5-cli php5-mysql php5-gd \
    php5-mcrypt php5-json \
    php-pear snmp fping \
    python-mysqldb \
    rrdtool subversion whois \
    mtr-tiny ipmitool \
    graphviz imagemagick && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt /var/lib/dpkg /var/lib/cache /var/lib/log

RUN mkdir -p /opt/observium
WORKDIR /opt
RUN wget http://www.observium.org/observium-community-latest.tar.gz && \
    tar zxvf observium-community-latest.tar.gz && \
    cp /opt/observium/config.php.default /opt/observium/config.php


