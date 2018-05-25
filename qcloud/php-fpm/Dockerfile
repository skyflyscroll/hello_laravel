FROM ccr.ccs.tencentyun.com/cluster-alpha/phpfpm:latest

LABEL maintainer="Mahmoud Zalt <mahmoud@zalt.me>"

ADD . /var/www/

WORKDIR /var/www/

RUN composer install \
	&& php artisan key:generate \
	&& chmod -R 777 storage

CMD ["php-fpm"]

EXPOSE 9000
