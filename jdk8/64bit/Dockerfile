FROM debian:jessie

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle/jre
ENV JAVA_HOME_LIB $JAVA_HOME/lib

RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee /etc/apt/sources.list.d/webupd8team-java.list && \
    echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list && \
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 && \
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections

RUN apt-get update && \
	apt-get install -y \
        libssl-dev \
        oracle-java8-installer \
        maven && \
	apt-get clean
RUN update-alternatives --set java $JAVA_HOME/bin/java
