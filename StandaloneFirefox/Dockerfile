FROM selenium/standalone-firefox:latest
USER seluser

WORKDIR /tmp

# Install Ruby
RUN sudo apt-get update \
 && sudo apt-get -y install build-essential \
                       automake \
                       zlib1g-dev \
                       libssl-dev \
 && sudo apt-get clean \
 && wget --no-check-certificate -q https://cache.ruby-lang.org/pub/ruby/2.6/ruby-2.6.3.tar.gz \
 && tar zxvf ruby-2.6.3.tar.gz \
 && cd ruby-2.6.3 \
 && ./configure \
 && make \
 && sudo make install \
 && cd .. \
 && rm -fr ruby-2.6.3*

# Set working directory
WORKDIR /opt/bin
