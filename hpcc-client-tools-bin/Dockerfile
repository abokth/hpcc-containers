FROM centos:centos7

USER root
RUN yum -y update

RUN yum -y install epel-release

RUN mkdir /opt/dist
WORKDIR /opt/dist
ADD https://d2wulyp08c6njk.cloudfront.net/releases/CE-Candidate-7.6.16/bin/clienttools/hpccsystems-clienttools-community_7.6.16-1.el7.x86_64.rpm .
ADD sha256sums .
RUN sha256sum --check sha256sums
RUN yum -y localinstall *.rpm

WORKDIR /
RUN yum clean all

RUN useradd hpcc
USER hpcc
WORKDIR /home/hpcc
