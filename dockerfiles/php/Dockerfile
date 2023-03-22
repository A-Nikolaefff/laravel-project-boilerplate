FROM php:8.2-fpm

ARG UID
ARG GID

ENV UID=${UID}
ENV GID=${GID}

RUN apt-get update && apt-get install -y \
    curl \
    git \
    zip \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /var/www/html
WORKDIR /var/www/html

# Composer
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# The dialout group in Alpine Linux and the MacOS staff group both have gids of 20. Let's just get rid of it because we aren't using it.
RUN delgroup dialout

# Laravel user assignment
RUN addgroup --gid ${GID} --system laravel
RUN adduser --ingroup laravel --disabled-password --shell /bin/sh --uid ${UID} --system laravel

RUN sed -i "s/user = www-data/user = laravel/g" /usr/local/etc/php-fpm.d/www.conf
RUN sed -i "s/group = www-data/group = laravel/g" /usr/local/etc/php-fpm.d/www.conf
RUN echo "php_admin_flag[log_errors] = on" >> /usr/local/etc/php-fpm.d/www.conf

# Xdebug
RUN pecl install xdebug \ && docker-php-ext-enable xdebug

# PostgreSQL
RUN docker-php-ext-install pgsql
RUN docker-php-ext-install pdo_pgsql

# MySQL
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql

USER laravel

CMD ["php-fpm", "-y", "/usr/local/etc/php-fpm.conf", "-R"]

