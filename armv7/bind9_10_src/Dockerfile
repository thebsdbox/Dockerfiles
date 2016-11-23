FROM armv7/armhf-debian:latest
MAINTAINER <daniel.finneran@gmail.com>

########### Repeatable build environment #################

# Configure the environment
RUN apt-get update
RUN apt-get install -y make wget gcc libssl-dev libjson-c-dev perl-modules libjson0 libxml2-dev libxml2 nfs-common ruby-dev ruby

# Install FPM to build a deb package
RUN gem install fpm



########## Mutable compiliation steps #################

# Download the bind910 Source
RUN wget -O bind.tar.gz https://www.isc.org/downloads/file/bind-9-10-4-p2/?version=tar-gz
RUN tar -xvzf bind.tar.gz
WORKDIR /bind-9.10.4-P2

# Configure the build with XML/JSON ssl and capability support disabled
RUN ./configure --with-openssl --enable-threads --with-libxml2 --disable-linux-caps --with-libjson=yes
RUN make

# Create a temporary location and install files
RUN mkdir /tmp/installdir
RUN make install DESTDIR=/tmp/installdir

# Strip the binaries from 152M to 44M
RUN find /tmp/installdir -executable -exec strip -s {} \;

# Use FPM to build a deb package
RUN fpm -s dir -t deb -n bind9 -v0.9.10-dan -C /tmp/installdir -p bind9_10_VERSION_ARCH.deb etc usr var
