FROM ccr.ccs.tencentyun.com/yuki_laravel/php-fpm:latest

LABEL maintainer="Mahmoud Zalt <mahmoud@zalt.me>"

COPY . /var/www

WORKDIR /var/www

RUN apt update && apt install composer && composer install

RUN chmod -R 777 storage

RUN php artisan generate:key



CMD ["php-fpm"]

EXPOSE 9000
