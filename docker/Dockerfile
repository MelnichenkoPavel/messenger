FROM php:7.4-fpm

RUN set -eux; \
	apt-get update; \
	apt-get install -y git wget libzip-dev librabbitmq-dev; \
	docker-php-ext-install -j$(nproc) zip; \
    pecl install amqp xdebug; \
    docker-php-ext-enable amqp xdebug; \
    rm -rf /var/lib/apt/lists/*

ADD php.ini /usr/local/etc/php/php.ini

RUN set -eux; \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/bin --filename=composer

RUN set -eux; \
    wget https://get.symfony.com/cli/installer -O - | bash; \
    mv /root/.symfony/bin/symfony /usr/local/bin/symfony
