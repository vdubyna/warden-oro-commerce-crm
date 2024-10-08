FROM docker.io/wardenenv/php-fpm:8.3

USER root

RUN set -eux \
    && dnf install -y postgresql php-pgsql \
    && dnf clean all \
    && rm -rf /var/cache/dnf

USER www-data