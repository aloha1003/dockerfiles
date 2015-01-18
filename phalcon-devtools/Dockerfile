FROM php:5.6

# Install Phalcon Extension
RUN \
    apt-get update && \
    apt-get install -y \
        libpcre3-dev \
        git \
        gcc \
        make && \
    git clone --depth=1 git://github.com/phalcon/cphalcon.git && \
    cd cphalcon/build && \
    ./install && \
    git clone https://github.com/phalcon/phalcon-devtools.git /usr/local/lib/phalcon-devtools && \
    ln -s /usr/local/lib/phalcon-devtools/phalcon.php /usr/bin/phalcon && \
    chmod +x /usr/bin/phalcon

COPY php.ini /usr/local/etc/php/

# Set up the application directory.
VOLUME ["/app"]
WORKDIR /app

# Set up the command arguments
CMD ["commands"]
ENTRYPOINT ["phalcon"]

