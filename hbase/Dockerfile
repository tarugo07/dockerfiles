FROM openjdk:8u191-jdk-alpine3.8

LABEL maintainer="Tomoyoshi Ogura <tomoyoshi.ogura@gmail.com>"

ARG HBASE_VERSION=1.2.0

RUN apk add --update --no-cache bash && \
    wget -q -O - http://archive.apache.org/dist/hbase/$HBASE_VERSION/hbase-$HBASE_VERSION-bin.tar.gz | tar --directory /usr/local -xzf - && \
    ln -s /usr/local/hbase-$HBASE_VERSION /usr/local/hbase && \
    mkdir -p /var/lib/zookeeper && \
    mkdir -p /var/lib/hbase

ENV PATH $PATH:/usr/local/hbase/bin

VOLUME /var/lib/hbase

ADD ./run.sh /run.sh
RUN chmod +x /run.sh

ADD ./hbase-site.xml /usr/local/hbase/conf/
ADD ./hbase-env.sh /usr/local/hbase/conf/

EXPOSE 2181 2888 3888 16000 16010 16020 16030

CMD ["/run.sh"]
