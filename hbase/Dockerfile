
FROM java:8-jdk
MAINTAINER Tomoyoshi Ogura

RUN wget --quiet -O - http://archive.apache.org/dist/hbase/1.2.4/hbase-1.2.4-bin.tar.gz | tar --directory /usr/local -xzf -
RUN ln -s /usr/local/hbase-1.2.4 /usr/local/hbase

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/jre

ENV PATH $PATH:/usr/local/hbase/bin

RUN mkdir /data
