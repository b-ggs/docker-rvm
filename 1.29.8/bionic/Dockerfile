FROM buildpack-deps:bionic

ENV RVM_VERSION=1.29.8

RUN curl -sSL https://github.com/rvm/rvm/archive/${RVM_VERSION}.tar.gz -o /tmp/rvm-stable.tar.gz \
  && mkdir -p /tmp/rvm \
  && cd /tmp/rvm \
  && tar --strip-components=1 -xzf /tmp/rvm-stable.tar.gz \
  && ./install --auto-dotfiles \
  && rm -rf /tmp/*

SHELL ["/bin/bash", "-l", "-c"]

RUN rvm requirements

RUN echo "source /usr/local/rvm/scripts/rvm" >> $HOME/.bashrc
