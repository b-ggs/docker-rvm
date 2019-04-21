FROM debian:stretch

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y procps curl gnupg2 \
  && rm -rf /var/lib/apt/lists/*

COPY dirmngr.conf $HOME/.gnupg/dirmngr.conf

RUN gpg2 --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

RUN curl -sSL https://get.rvm.io | bash -s stable

SHELL ["/bin/bash", "-l", "-c"]

RUN rvm requirements

CMD ["/bin/bash", "-l"]
