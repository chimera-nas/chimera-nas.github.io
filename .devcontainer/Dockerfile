FROM ubuntu:24.04

ADD Gemfile /Gemfile    
ADD Gemfile.lock /Gemfile.lock

ENV LC_ALL="C.UTF-8"
ENV LANG="en_US.UTF-8"
ENV LANGUAGE="en_US.UTF-8"

RUN apt-get -y update && \
    apt-get -y --no-install-recommends upgrade && \
    apt-get -y --no-install-recommends install unminimize && \
    echo y | unminimize && \
    apt-get -y --no-install-recommends install git ssh ruby-full build-essential zlib1g-dev && \
    gem install jekyll bundler && \
    bundler install
