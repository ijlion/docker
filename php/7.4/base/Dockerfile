FROM alpine:3.12

ADD https://dl.bintray.com/php-alpine/key/php-alpine.rsa.pub /etc/apk/keys/php-alpine.rsa.pub

RUN set -ex \
    && echo "https://dl.bintray.com/php-alpine/v3.12/php-7.4" >> /etc/apk/repositories \
    && echo "@php https://dl.bintray.com/php-alpine/v3.12/php-7.4" >> /etc/apk/repositories \
    && apk update \
    && apk add --no-cache \
# persistent / runtime deps
    ca-certificates \
    curl \
    wget \
    tar \
    xz \
    libressl \
    tzdata \
    pcre \
# php / extenstions
    php7 \
    php7-sodium \
    php7-bcmath \
    php7-ctype \
    php7-iconv \
    php7-json \
    php7-mbstring \
    php7-openssl \
    php7-pdo \
    php7-xml \
    php7-xmlreader \
    php7-zip \
    php7-zlib \
# clear
    && ln -sf /usr/bin/php7 /usr/bin/php \
    && apk del --purge *-dev \
    && rm -rf /var/cache/apk/* /tmp/* /usr/share/man /usr/share/php7 \
    && echo -e "\033[42;37m Base php build completed! \033[0m\n"