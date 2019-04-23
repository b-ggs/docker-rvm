FROM debian:stretch

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y procps curl tar \
  && rm -rf /var/lib/apt/lists/*

ENV RVM_VERSION=1.29.7

RUN curl -sSL https://github.com/rvm/rvm/archive/${RVM_VERSION}.tar.gz -o /tmp/rvm-stable.tar.gz \
  && mkdir -p /tmp/rvm \
  && cd /tmp/rvm \
  && tar --strip-components=1 -xzf /tmp/rvm-stable.tar.gz \
  && ./install --auto-dotfiles \
  && rm -rf /tmp/*

RUN /bin/bash -lc rvm requirements

RUN echo 'source /usr/local/rvm/scripts/rvm' >> $HOME/.bashrc
