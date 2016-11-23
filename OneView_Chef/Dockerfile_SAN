FROM armv7/armhf-debian:latest
MAINTAINER <daniel.jam.finneran@hpe.com>

RUN apt-get update
RUN apt-get -y install chef-zero ruby2.1-dev gcc make
RUN chef gem install chef-provisioning-oneview
