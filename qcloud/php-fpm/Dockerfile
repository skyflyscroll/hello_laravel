FROM ccr.ccs.tencentyun.com/yuki_laravel/php-fpm:latest

LABEL maintainer="Mahmoud Zalt <mahmoud@zalt.me>"

COPY . /var/www

WORKDIR /var/www

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
	&& php -r "if (hash_file('SHA384', 'composer-setup.php') === '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061') \
	{ echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
	&& php composer-setup.php \
	&& php -r "unlink('composer-setup.php');"
	
RUN ls

RUN php /var/www/composer.phar install

RUN chmod -R 777 storage

RUN php artisan generate:key



CMD ["php-fpm"]

EXPOSE 9000
