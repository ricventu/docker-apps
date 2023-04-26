FROM php:8.2-cli-alpine

RUN apk add --no-cache bash bash-completion grep git


RUN apk add --no-cache linux-headers $PHPIZE_DEPS \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN cp "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"
COPY config/xdebug.ini "$PHP_INI_DIR/conf.d/xdebug.ini"
ENV PHP_IDE_CONFIG="serverName=docker-apps-php"

COPY --from=composer/composer:2-bin /composer /usr/bin/composer
