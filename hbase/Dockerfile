
FROM java:openjdk-8-jdk-alpine
MAINTAINER Tomoyoshi Ogura

ENV JAVA_HOME /usr/lib/jvm/java-1.8-openjdk

RUN wget -q -O - http://archive.apache.org/dist/hbase/1.2.4/hbase-1.2.4-bin.tar.gz | tar --directory /usr/local -xzf -
RUN ln -s /usr/local/hbase-1.2.4 /usr/local/hbase

ENV PATH $PATH:/usr/local/hbase/bin

RUN mkdir /data

EXPOSE 2181
EXPOSE 60000
EXPOSE 60010
EXPOSE 60020
EXPOSE 60030

CMD /usr/local/hbase/bin/start-hbase.sh
