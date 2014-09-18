FROM centos:centos6

RUN rpm -ivh http://fedora-epel.mirror.lstn.net/6/i386/epel-release-6-8.noarch.rpm
RUN yum -y update
RUN yum install -y wget curl vim

RUN wget http://s3.amazonaws.com/influxdb/influxdb-0.8.2-1.x86_64.rpm
#RUN wget http://s3.amazonaws.com/influxdb/influxdb-0.7.3-1.x86_64.rpm
RUN rpm -ivh influxdb-0.8.2-1.x86_64.rpm

ADD my_config.toml /opt/influxdb/shared/config.toml

#EXPOSE 8083 8086

ENTRYPOINT ["/usr/bin/influxdb"]
CMD ["-pidfile", "/tmp/influxdb.pid", "-config", "/opt/influxdb/shared/config.toml" ]
