FROM registry.cn-qingdao.aliyuncs.com/iamapap/rockylinux:8.7-base-20221113

LABEL com.gdcapf.author="zhengwei" \
      com.gdcapf.build-date="20230213" \
      com.gdcapf.java-name="openjdk" \
	  com.gdcapf.java-version="jdk8u362-b09"

ENV JAVA_HOME /usr/local/openjdk
ENV CLASSPATH .:$JAVA_HOME/lib:$JAVA_HOME/jre/lib:$CLASSPATH
ENV PATH $JAVA_HOME/bin:$JAVA_HOME/jre/bin:$PATH
ENV LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8'

RUN dnf install -y openssl curl wget ca-certificates fontconfig gzip tar \
    && dnf clean all

ENV JAVA_VERSION jdk8u362-b09

RUN wget -O /tmp/openjdk.tar.gz https://github.com/adoptium/temurin8-binaries/releases/download/jdk8u362-b09/OpenJDK8U-jdk_x64_linux_hotspot_8u362b09.tar.gz; \
    mkdir -p "$JAVA_HOME"; \
    tar --extract --file /tmp/openjdk.tar.gz --directory "$JAVA_HOME" --strip-components 1 --no-same-owner; \
    rm -f /tmp/openjdk.tar.gz ${JAVA_HOME}/src.zip;

RUN echo Verifying install ... \
    && echo javac -version && javac -version \
    && echo java -version && java -version \
    && echo Complete.