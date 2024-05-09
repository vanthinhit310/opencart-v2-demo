# Use the official PHP 7.4 image from Docker Hub
FROM php:7.4-fpm

# Install dependencies
RUN apt-get update && apt-get install -y \
    libzip-dev \
    libxml2-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libonig-dev \
    libgd-dev \
    default-mysql-client \
    libcurl4-openssl-dev \
    libssl-dev \
    zlib1g-dev \
    openssl \
    libmcrypt-dev

# Install extensions
RUN docker-php-ext-install pdo_mysql mbstring zip exif pcntl
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install gd
RUN docker-php-ext-install json
RUN docker-php-ext-install xml
RUN docker-php-ext-install curl
RUN docker-php-ext-install iconv
RUN docker-php-ext-install zip

# Install mcrypt
RUN pecl install mcrypt-1.0.4 \
    && docker-php-ext-enable mcrypt

# Install Xdebug
RUN pecl install xdebug-2.9.8 \
    && docker-php-ext-enable xdebug

# Use the default production configuration
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

# Switch to the /var/www directory
WORKDIR /var/www/html

# Change the ownership of the application files to the nginx user
RUN chown -R www-data:www-data /var/www/html

# Expose port 9000 and start php-fpm server
EXPOSE 9000
CMD ["php-fpm"]