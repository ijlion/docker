FROM alpine:3.11

ADD https://dl.bintray.com/php-alpine/key/php-alpine.rsa.pub /etc/apk/keys/php-alpine.rsa.pub

RUN set -ex \
    && echo "https://dl.bintray.com/php-alpine/v3.11/php-7.4" >> /etc/apk/repositories \
    && echo "@php https://dl.bintray.com/php-alpine/v3.11/php-7.4" >> /etc/apk/repositories \
    && apk update \
    && apk add --no-cache \
    ca-certificates \
    curl \
    wget \
    tar \
    xz \
    libressl \
    tzdata \
    pcre \
    php7 \
    php7-bcmath \
    php7-bz2 \
    php7-curl \
    php7-ctype \
    php7-dom \
    php7-ds \
    php7-exif \
    php7-gd \
    php7-iconv \
    php7-intl \
    php7-json \
    php7-mbstring \
    php7-openssl \
    php7-pcntl \
    php7-pdo \
    php7-pdo_mysql \
    php7-pdo_sqlite \
    php7-phar \
    php7-psr \
    php7-posix \
    php7-redis \
    php7-sockets \
    php7-sodium \
    php7-sysvshm \
    php7-sysvmsg \
    php7-sysvsem \
    php7-xml \
    php7-xmlreader \
    php7-zip \
    php7-zlib \
    && mv /etc/php7/conf.d/00_ds.ini /etc/php7/conf.d/10_ds.ini \
    && ln -sf /usr/bin/php7 /usr/bin/php \
    && apk del --purge *-dev \
    && rm -rf /var/cache/apk/* /tmp/* /usr/share/man /usr/share/php7 \
    && echo -e "\033[42;37m Done! \033[0m\n"

WORKDIR /app