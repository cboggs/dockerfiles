FROM centos:centos6

RUN rpm -ivh http://fedora-epel.mirror.lstn.net/6/i386/epel-release-6-8.noarch.rpm
RUN yum -y update
RUN yum install -y protobuf protobuf-compiler protobuf-devel protobuf bzr bzip2 bzip2-devel bison valgrind flex autoconf automake gcc-c++ wget zlib-devel libtool git  curl tar glibc-devel which

WORKDIR /root

ADD go1.3.linux-amd64.tar.gz /usr/local
ADD influxdb-0.8.0-rc.3.tar.gz /root

ENV PATH $PATH:/usr/local/go/bin
ENV GOPATH /root/gocodez
RUN export

RUN mkdir -p /root/gocodez/src/github.com/influxdb

WORKDIR /root/gocodez/src/github.com/influxdb
RUN git clone git://github.com/influxdb/influxdb

WORKDIR /root/gocodez/src/github.com/influxdb/influxdb
RUN ./configure
RUN make build
RUN make test

ENTRYPOINT ["/root/gocodez/src/github.com/influxdb/influxdb/influxdb"]