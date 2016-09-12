###########################################
# Dockerfile to build Jenkins master image
# Based on Debian:8(jessie)
###########################################

FROM registry.aliyuncs.com/acs-sample/jenkins:base
MAINTAINER XinYe <nunchuk@live.com>

COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt

COPY debian8-lts.list /etc/apt/sources.list
RUN apt-get update -y && \
    apt-get install bash libc6 libc-bin openssl wget ntp -y && \
	rm -rf /var/lib/apt/lists/* && \
	rm /etc/localtime && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
COPY ntp.conf /etc/ntp.conf
