FROM selenium/standalone-chrome:latest
USER seluser

WORKDIR /tmp

# Install Ruby
RUN sudo apt-get update \
 && sudo apt-get -y install build-essential \
                       automake \
                       zlib1g-dev \
                       libssl-dev \
 && sudo apt-get clean \
 && wget --no-check-certificate -q https://cache.ruby-lang.org/pub/ruby/2.7/ruby-2.7.6.tar.gz \
 && tar zxvf ruby-2.7.6.tar.gz \
 && cd ruby-2.7.6 \
 && ./configure \
 && make \
 && sudo make install \
 && cd .. \
 && rm -fr ruby-2.7.6*

# Install gems
RUN sudo gem install selenium-webdriver ruby-gmail debase debugger-ruby_core_source rake ruby-debug-ide httparty mailgunner rest-client

# Install Git
RUN sudo apt-get install -y git

# Set working directory
WORKDIR /opt/bin
