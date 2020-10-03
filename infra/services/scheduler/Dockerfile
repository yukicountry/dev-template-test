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
    ${PHPIZE_DEPS} \
    imagemagick-dev && \
  # change timezone UTC to JST
  cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  echo "Asia/Tokyo" > /etc/timezone && \
  # php extensions required for laravel installation
  docker-php-ext-install bcmath gd pdo_mysql && \
  # install redis php extension
  pecl install redis imagick && \
  docker-php-ext-enable redis imagick && \
  # cleaning
  apk del tzdata pcre-dev ${PHPIZE_DEPS} && \
  rm -rf /tmp/pear

RUN (crontab -l && echo "* * * * * cd /work/backend && php artisan schedule:run >> /var/log/cron-std-stderr.log 2>&1") | crontab -

WORKDIR /work/backend

CMD ["crond", "-f"]
