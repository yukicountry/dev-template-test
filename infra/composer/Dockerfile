FROM php:7.3-alpine
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

# add composer
RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer

WORKDIR /work/backend

CMD ["echo", "This container is not for daemon and will exit."]
