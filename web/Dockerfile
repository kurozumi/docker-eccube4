FROM php:7-apache
RUN a2enmod rewrite

RUN set -x \
	&& apt-get update \
	&& apt-get install -y --no-install-recommends \
        sudo \
        git \
        vim \
        libxml2-dev \
        unzip \
        wget \
        zlib1g-dev \
        iproute \
        libsqlite3-dev \
        libpq-dev \
        libicu-dev \
        gnupg2 \
        libzip-dev

RUN docker-php-ext-install \
    intl \
    mbstring \
    pdo \
    pdo_sqlite \
    pdo_mysql \
    pdo_pgsql \
    mysqli \
    soap \
    xml \
    zip

RUN curl -sS https://getcomposer.org/installer | php -- \
        --install-dir=/usr/local/bin \
        --filename=composer

RUN composer global require --optimize-autoloader \
        "hirak/prestissimo"

WORKDIR /var/www/html

RUN ls -lt ${PHP_INI_DIR}/conf.d/
COPY config/php.ini ${PHP_INI_DIR}/

EXPOSE 80

ENV MAILER_URL null://mailcatcher:1025

CMD ["apachectl", "-D", "FOREGROUND"]
