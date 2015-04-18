FROM centos:latest

ADD mongo.repo /etc/yum.repos.d/mongo.repo
RUN yum update -y && yum install mongodb-org numactl -y --nogpgcheck
RUN yum clean metadata
RUN yum clean all

VOLUME ["/data/db/"]
WORKDIR /data

EXPOSE 27017
EXPOSE 28017

ENTRYPOINT ["/usr/bin/numactl", "--interleave", "all",  "/usr/bin/mongod", "--storageEngine", "wiredTiger", "--logpath", "/data/log", "--smallfiles", "--dbpath", "/data/db", "--quiet"]
