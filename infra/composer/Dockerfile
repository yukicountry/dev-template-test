FROM php:7.3-fpm-alpine
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

RUN apk upgrade --update && \
  apk --no-cache add \
    tzdata \
    zip \
    freetype-dev \
    libjpeg-turbo-dev \
    libpng-dev && \
  # change timezone UTC to JST
  cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  echo "Asia/Tokyo" > /etc/timezone && \
  apk del tzdata && \
  # php extensions required for laravel installation
  docker-php-ext-install bcmath gd pdo_mysql

# add composer
RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer

WORKDIR /work/backend

CMD ["echo", "This container is not for daemon and will exit."]
