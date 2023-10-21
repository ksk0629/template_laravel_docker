# Define the image file.
FROM php:8.0-apache

# Add setting files into the contianer.
ADD php.ini /usr/local/etc/php/
ADD 000-default.conf /etc/apache2/sites-enabled/

# Install composer.
RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer

# Install middlewares.
RUN apt-get update \
&& apt-get install -y \
git \
zip \
unzip \
vim \
libpng-dev \
libpq-dev \
&& docker-php-ext-install pdo_mysql

# Enable modRewrite for Laravel.
RUN mv /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled
RUN /bin/sh -c a2enmod rewrite

# Install Laravel using composer.
RUN composer require laravel/installer

# Add the composer path to the environment variables.
RUN export PATH=/var/www/html/vendor/bin:$PATH
