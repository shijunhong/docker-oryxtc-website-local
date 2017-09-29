FROM php:7-fpm
RUN apt-get update && apt-get install -y \
		libfreetype6-dev \
		libjpeg62-turbo-dev \
		libpng12-dev \
		vsftpd \
	&& pecl install redis-3.1.3 \
	&& docker-php-ext-install -j$(nproc) bcmath pdo pdo_mysql fileinfo zip\
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd \
	&& docker-php-ext-enable redis