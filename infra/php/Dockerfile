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

# zz-docker.confの設定を上書きするためファイル名zzz-www.confとしてコピー
COPY ./php-fpm.d/www.conf /usr/local/etc/php-fpm.d/zzz-www.conf

WORKDIR /work/backend
