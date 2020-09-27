FROM php:7.3-fpm

COPY --from=composer:1.10 /usr/bin/composer /usr/bin/composer

# zz-docker.confの設定を上書きするためファイル名zzz-www.confとしてコピー
COPY ./www.conf /usr/local/etc/php-fpm.d/zzz-www.conf
