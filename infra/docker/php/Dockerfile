FROM php:7.3-fpm-alpine
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

RUN apk upgrade --update && \
  apk --no-cache add tzdata zip && \
  # change timezone UTC to JST
  cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  echo "Asia/Tokyo" > /etc/timezone && \
  apk del tzdata && \
  # add composer
  php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer && \
  # php extensions required for laravel installation
  docker-php-ext-install bcmath

# zz-docker.confの設定を上書きするためファイル名zzz-www.confとしてコピー
COPY ./php-fpm.d/www.conf /usr/local/etc/php-fpm.d/zzz-www.conf

WORKDIR /work/backend
