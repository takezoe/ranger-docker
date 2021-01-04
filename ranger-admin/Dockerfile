FROM maven:3.6.2-jdk-8
LABEL maintainer-twitter="@takezoen"
LABEL version=2.1.0

ARG RANGER_VERSION=2.1.0

ADD https://repo1.maven.org/maven2/mysql/mysql-connector-java/8.0.21/mysql-connector-java-8.0.21.jar /opt

ADD http://mirrors.whoishostingthis.com/apache/ranger/${RANGER_VERSION}/apache-ranger-${RANGER_VERSION}.tar.gz /opt

COPY ranger-entrypoint.sh /opt

WORKDIR /opt

RUN apt-get -q update && apt-get install -y -q python gcc \
 && tar zxvf apache-ranger-${RANGER_VERSION}.tar.gz \
 && cd apache-ranger-${RANGER_VERSION} \
 && export MAVEN_OPTS="-Xmx2G" \
 && mvn package -DskipTests \
 && cp target/ranger-${RANGER_VERSION}-admin.tar.gz /opt \
 && cd /opt \
 && tar zxvf ranger-${RANGER_VERSION}-admin.tar.gz \
 && chmod +x /opt/ranger-entrypoint.sh

ENV JAVA_HOME=/usr/local/openjdk-8
ENV RANGER_HOME=/opt/ranger-${RANGER_VERSION}-admin

COPY install.properties ${RANGER_HOME}

EXPOSE 6080

ENTRYPOINT ["/opt/ranger-entrypoint.sh"]
