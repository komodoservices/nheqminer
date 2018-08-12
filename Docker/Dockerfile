FROM ubuntu:xenial

MAINTAINER Asher Dawes <asher.dawes@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

WORKDIR /usr/include/

ENV BOOST_VERSION=1.66
ENV BOOST_VERSION_=1.66_
ENV BOOST_ROOT=/usr/include/boost

RUN apt-get -qq update && apt-get install -q -y software-properties-common python-software-properties
RUN add-apt-repository ppa:ubuntu-toolchain-r/test -y
RUN apt-get -qq update && apt-get install -qy g++-6 gcc git wget

RUN update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-6 90

RUN wget --no-check-certificate --max-redirect 3 https://sourceforge.net/projects/boost/files/boost/${BOOST_VERSION}/boost_${BOOST_VERSION_}.tar.gz


RUN mkdir -p /usr/include/boost && tar zxf boost_${BOOST_VERSION_}.tar.gz -C /usr/include/boost --strip-components=1

RUN echo ${BOOST_ROOT}


ENTRYPOINT /bin/bash