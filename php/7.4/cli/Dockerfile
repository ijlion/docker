FROM alpine:3.11

ADD https://dl.bintray.com/php-alpine/key/php-alpine.rsa.pub /etc/apk/keys/php-alpine.rsa.pub

RUN apk --update-cache add ca-certificates && \
    echo "https://dl.bintray.com/php-alpine/v3.11/php-7.4" >> /etc/apk/repositories

RUN set -ex && apk add --no-cache \
    php7 \
    php7-sodium \
    php7-bcmath \
    php7-ctype \
    php7-iconv \
    php7-json \
    php7-mbstring \
    php7-pdo \
    php7-xml \
    php7-xmlreader \
    php7-zip \
    php7-zlib \
    && ln -sf /usr/bin/php7 /usr/bin/php \
    && apk del --purge *-dev \
    && rm -rf /var/cache/apk/* /tmp/* /usr/share/man /usr/share/php7

COPY docker-php-ext-install /usr/local/bin/