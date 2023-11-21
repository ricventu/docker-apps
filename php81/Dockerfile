FROM php:8.1-cli-alpine

RUN apk add --no-cache bash bash-completion grep git

RUN apk add --no-cache linux-headers $PHPIZE_DEPS

ARG INSTALL_REDIS=true
RUN if [ "$INSTALL_REDIS" = "true" ]; then \
    pecl install -o -f redis \
    && rm -rf /tmp/pear \
    && docker-php-ext-enable redis \
    ;fi

ARG INSTALL_XDEBUG=true
RUN if [ "$INSTALL_XDEBUG" = "true" ]; then \
    pecl install xdebug \
    && docker-php-ext-enable xdebug \
    ;fi

RUN cp "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"
COPY config/xdebug.ini "$PHP_INI_DIR/conf.d/xdebug.ini"
ENV PHP_IDE_CONFIG="serverName=docker-apps-php81"

COPY --from=composer/composer:2-bin /composer /usr/bin/composer
