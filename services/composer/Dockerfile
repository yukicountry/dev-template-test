FROM php:7.3-fpm-alpine
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

RUN apk upgrade --update && \
  apk --no-cache add \
    tzdata \
    zip \
    freetype-dev \
    libjpeg-turbo-dev \
    libpng-dev \
    pcre-dev \
    ${PHPIZE_DEPS} && \
  # change timezone UTC to JST
  cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  echo "Asia/Tokyo" > /etc/timezone && \
  # php extensions required for laravel installation
  docker-php-ext-install bcmath gd pdo_mysql && \
  # install redis php extension
  pecl install redis && \
  docker-php-ext-enable redis && \
  # cleaning
  apk del tzdata pcre-dev ${PHPIZE_DEPS} && \
  rm -rf /tmp/pear

# add composer
RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer

WORKDIR /work/backend

CMD ["echo", "This container is not for daemon and will exit."]
