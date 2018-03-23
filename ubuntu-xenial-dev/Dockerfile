FROM ubuntu:16.04

MAINTAINER kaszpir@gmail.com

ENV LANG C.UTF-8
ENV TERM xterm

RUN DEBIAN_FRONTENTD=noninteractive apt-get update && apt-get -y install --no-install-recommends \
  build-essential \
  graphviz \
  git \
  python-dev \
  python-pip \
  && apt-get autoclean && apt-get clean && rm -rf /var/lib/apt/lists/* \
  && pip install --upgrade pip \
  && pip install setuptools
